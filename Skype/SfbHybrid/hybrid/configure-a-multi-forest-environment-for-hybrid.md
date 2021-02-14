---
title: Distribuire una topologia di foresta di risorse
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: Le sezioni seguenti forniscono indicazioni su come configurare un ambiente con più foreste in un modello di foresta di risorse/utenti per fornire funzionalità skype for Business in uno scenario ibrido.
ms.openlocfilehash: cf3a162001756661afd0f204e9968713d9db0f5b
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221480"
---
# <a name="deploy-a-resource-forest-topology"></a>Distribuire una topologia di foresta di risorse
 
Le sezioni seguenti forniscono indicazioni su come configurare un ambiente con più foreste in un modello di foresta di risorse/utenti per fornire funzionalità skype for Business in uno scenario ibrido. 
  
![Ambiente a più foreste per ambiente ibrido](../../sfbserver/media/5f079435-b252-4a6a-9638-3577d55b2873.png)
  
## <a name="topology-requirements"></a>Requisiti per la topologia

Sono supportate più foreste utente. Tenere presente quanto segue: 
    
- Per le versioni supportate di Lync Server e Skype for Business Server in una configurazione ibrida, vedere i requisiti della versione [server](plan-hybrid-connectivity.md#server-version-requirements) in Pianificare la connettività ibrida tra Skype for Business Server e [Microsoft 365 o Office 365.](plan-hybrid-connectivity.md)
    
- Exchange Server possono essere distribuite in una o più foreste, che possono includere o meno la foresta contenente Skype for Business Server. Assicurarsi di aver applicato l'aggiornamento cumulativo più recente.
    
- Per informazioni dettagliate sulla coesistenza con Exchange Server, inclusi i criteri e le limitazioni di supporto in varie combinazioni di locale e online, vedere Supporto delle funzionalità [in](../../sfbserver/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support) Pianificare l'integrazione di Skype for Business ed [Exchange.](../../sfbserver/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md)
    
  
## <a name="user-homing-considerations"></a>Considerazioni sull'homing degli utenti

Gli utenti di Skype for Business ospitati in locale possono disporre di Exchange in locale o online. Gli utenti di Skype for Business online devono usare Exchange Online per un'esperienza ottimale; Tuttavia, questa operazione non è obbligatoria. Exchange locale non è necessario per implementare Skype for Business in entrambi i casi.
  
## <a name="configure-forest-trusts"></a>Configurare trust tra foreste

In una topologia di foresta di risorse, le foreste di risorse che ospitano Skype for Business Server devono considerare attendibile ogni foresta di account che contiene gli account degli utenti che vi accederanno. Se si dispone di più foreste utente, per abilitare l'autenticazione tra foreste è importante che il routing dei suffissi nome sia abilitato per ognuna di queste relazioni di trust tra foreste. Per istruzioni, vedere [Managing Forest Trusts.](https://technet.microsoft.com/library/cc772440.aspx) Se è stata Exchange Server distribuita in un'altra foresta e fornisce funzionalità per gli utenti di Skype for Business, la foresta che ospita Exchange deve considerare attendibile la foresta che ospita Skype for Business Server. Ad esempio, se Exchange è stato distribuito nella foresta account, ciò significa effettivamente che è necessario un trust bidirezionale tra gli account e le foreste di Skype for Business in tale configurazione.
  
## <a name="synchronize-accounts-into-the-forest-hosting-skype-for-business"></a>Sincronizzare gli account nella foresta che ospita Skype for Business

Quando Skype for Business Server viene distribuito in una foresta (una foresta di risorse), ma fornisce funzionalità agli utenti in una o più altre foreste (foreste di account), gli utenti nelle altre foreste devono essere rappresentati come oggetti utente disabilitati nella foresta in cui è distribuito Skype for Business Server. È necessario distribuire e configurare un prodotto di gestione delle identità, ad esempio Microsoft Identity Manager, per eseguire il provisioning e la sincronizzazione degli utenti dalle foreste di account nella foresta in cui è distribuito Skype for Business Server. Gli utenti devono essere sincronizzati nella foresta che ospita Skype for Business Server come oggetti utente disabilitati. Gli utenti non possono essere sincronizzati come oggetti contatto di Active Directory, perché Azure Active Directory Connect non sincronizza correttamente i contatti in Azure AD per l'uso con Skype.
  
Indipendentemente da qualsiasi configurazione a più foreste, la foresta che ospita Skype for Business Server può anche fornire funzionalità per tutti gli utenti abilitati presenti nella stessa foresta.
  
Per ottenere la corretta sincronizzazione delle identità, è necessario sincronizzare gli attributi seguenti: 
  
|**Foreste utente**|**Foreste di risorse**|
|:-----|:-----|
|attributo del collegamento all'account scelto  <br/> |attributo del collegamento all'account scelto  <br/> |
|posta elettronica  <br/> |posta elettronica  <br/> |
|ProxyAddresses  <br/> |ProxyAddresses  <br/> |
|ObjectSID  <br/> |msRTCSIP-OriginatorSID  <br/> |
   
[L'attributo di collegamento dell'account](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-design-concepts) scelto verrà utilizzato come ancoraggio di origine. Se si dispone di un attributo diverso e non modificabile che si preferisce utilizzare, è possibile farlo; è sufficiente assicurarsi di modificare la regola delle attestazioni AD FS e selezionare l'attributo durante la configurazione di AAD Connect.
  
Non sincronizzare gli UPN tra le foreste. Durante i test è stato rilevato che era necessario utilizzare un UPN univoco per ogni foresta utente, in quanto non è possibile utilizzare lo stesso UPN in più foreste. Di conseguenza, ci sono state presentate due possibilità: sincronizzare l'UPN o non eseguire la sincronizzazione. 
  
- Se l'UPN univoco di ogni foresta utente non è stato sincronizzato con l'oggetto disabilitato associato nella foresta di risorse, single sign-on (SSO) verrebbe interrotto almeno per il tentativo di accesso iniziale (presupponendo che l'utente abbia selezionato l'opzione per salvare la password). Nel client Skype for Business si presuppone che i valori SIP/UPN siano gli stessi. Poiché l'indirizzo SIP in questo scenario è user@company.com, ma l'UPN dell'oggetto abilitato nella foresta utenti è in realtà user@contoso.company.com, il tentativo di accesso iniziale avrà esito negativo e all'utente verrà richiesto di immettere le credenziali. Quando si immette l'UPN corretto/effettivo, la richiesta di autenticazione viene completata nei controller di dominio nella foresta utente e l'accesso ha esito positivo.
    
- Se l'UPN univoco di ogni foresta utente è stato sincronizzato con l'oggetto disabilitato associato nella foresta di risorse, l'autenticazione DI FS avrà esito negativo. La regola corrispondente trova l'UPN dell'oggetto nella foresta di risorse, che è stato disabilitato e non può essere utilizzato per l'autenticazione. 
    
## <a name="create-a-microsoft-365-or-office-365-organization"></a>Creare un'organizzazione di Microsoft 365 o Office 365

Sarà quindi necessario effettuare il provisioning di un'organizzazione di Microsoft 365 o Office 365 da usare con la distribuzione. Per altre informazioni, vedere [Sottoscrizioni, licenze, account](https://docs.microsoft.com/office365/enterprise/subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings)e tenant per le offerte cloud di Microsoft. 
  
## <a name="configure-active-directory-federation-services"></a>Configurare Active Directory Federation Services

Dopo aver creato un tenant, sarà necessario configurare Active Directory Federation Services (AD FS) in ogni foresta utente. Si presuppone che l'utente abbia un indirizzo SIP e SMTP univoco e un nome dell'entità utente (UPN) per ogni foresta. AD FS è facoltativo e viene usato qui per ottenere Single #A0 (SSO). È supportato anche DirSync con sincronizzazione password e può essere usato al posto di AD FS. 
  
Sono state testate solo le distribuzioni con SIP/SMTP e UPN corrispondenti. La presenza di SIP/SMTP/UPN corrispondenti può comportare funzionalità ridotte, ad esempio problemi con l'integrazione di Exchange e SSO. 
  
A meno che non si utilizzi un SIP/SMTP/UPN univoco per gli utenti di ogni foresta, è comunque possibile che si siano verificati problemi SSO, indipendentemente dalla posizione in cui è distribuito ADFS: 
  
- Trust unidirezionale o bidirezionale tra foreste di risorse/utenti con farm AD FS distribuita in ogni foresta utente, tutti gli utenti condividono il dominio SIP/SMTP comune ma UPN univoco per ogni foresta utente. 
    
- Trust bidirezionale tra foreste di risorse/utenti con farm AD FS distribuita solo nella foresta di risorse, tutti gli utenti condividono il dominio SIP/SMTP comune, ma UPN univoco per ogni foresta utente. 
    
Inserendo una farm AD FS in ogni foresta utente e utilizzando un SIP/SMTP/UPN univoco per ogni foresta, vengono risolti entrambi i problemi. Durante i tentativi di autenticazione, verranno cercati e cercati solo gli account nella foresta utente specifica. Ciò consente di fornire un processo di autenticazione più semplice. 
  
Si tratta di una distribuzione standard di AD FS di Windows Server 2012 R2 e dovrebbe funzionare prima di continuare. Per istruzioni, vedere [Come installare ADFS 2012 R2 per Microsoft 365 o Office 365.](https://blogs.technet.com/b/rmilne/archive/2014/04/28/how-to-install-adfs-2012-r2-for-office-365.aspx) 
  
Dopo la distribuzione, è necessario modificare la regola delle attestazioni in modo che corrisponda all'ancoraggio di origine selezionato in precedenza. In MMC AD FS, in Attendibilità componente, fare clic con il pulsante destro del mouse su **Microsoft 365 Identity Platform** o Microsoft Office **365 Identity Platform** e quindi scegliere Modifica regole **attestazione.** Modificare la prima regola e ObjectSID in **employeeNumber**. 
  
![Schermata Modifica regole a più foreste](../../sfbserver/media/f5d485bd-52cc-437f-ba71-217f8902056c.png)
  
## <a name="configure-aad-connect"></a>Configurare AAD Connect

Nelle topologie a foresta di risorse, è necessario che gli attributi utente della foresta di risorse e di tutte le foreste di account siano sincronizzati in Azure AD. Il modo più semplice e consigliato per eseguire questa operazione è  sincronizzare e unire le identità utente di Azure AD Connect da tutte le foreste che hanno abilitato gli account utente e la foresta che contiene Skype for Business. Per informazioni dettagliate, [vedere Configurare Azure AD Connect per Skype for Business e Teams.](configure-azure-ad-connect.md)

Si noti che AAD Connect non fornisce la sincronizzazione locale tra le foreste di account e risorse. Che deve essere configurato separatamente con Microsoft Identity Manager o un prodotto simile, come descritto in precedenza.
  
Al termine dell'unione di AAD Connect, se si osserva un oggetto nel metaverse, verrà visualizzato un elemento simile al seguente: 
  
![Schermata dell'oggetto Metaverse a più foreste](../../sfbserver/media/16379880-2de3-4c43-b219-1551f5dec5f6.png)
  
Gli attributi evidenziati in verde sono stati uniti da Microsoft 365 o Office 365, i gialli sono della foresta utente e il blu sono della foresta di risorse. 
  
Si tratta di un utente di test e si può vedere che AAD Connect ha identificato sourceAnchor e cloudSourceAnchor dall'utente e gli oggetti foresta di risorse da Microsoft 365 o Office 365, nel nostro caso 1101, che è il employeeNumber selezionato in precedenza. È stato quindi in grado di unire questo oggetto a quello visualizzato in precedenza. 
  
Per ulteriori informazioni, vedere Integrare le [directory locali con Azure Active Directory.](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect/) 
  
AAD Connect deve essere installato utilizzando le impostazioni predefinite, ad eccezione dei seguenti: 
  
1. Single #A0 - con AD FS già distribuito e funzionante: selezionare **Non configurare.**
    
2. Connettere le directory: aggiungere tutti i domini.
    
3. Identificare gli utenti nelle directory locali: selezionare le identità utente presenti in più **directory** e selezionare gli attributi **ObjectSID** e **msExchangeMasterAccountSID.**
    
4. Identificare gli utenti in Azure AD: ancoraggio origine: selezionare l'attributo scelto dopo aver letto Selezionando un attributo [sourceAnchor](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-design-concepts#selecting-a-good-sourceanchor-attribute)valido, Nome entità utente - **userPrincipalName.**
    
5.  Funzionalità facoltative: selezionare se exchange ibrido è stato distribuito.
    
    > [!NOTE]
    >  Se si dispone solo di Exchange Online, potrebbe verificarsi un problema con errori OAuth durante l'individuazione automatica a causa del reindirizzamento CNAME. Per risolvere il problema, è necessario impostare l'URL di individuazione automatica di Exchange eseguendo il cmdlet seguente da Skype for Business Server Management Shell:
    >
    > ```powershell
    > Set-CsOAuthConfiguration -ExchangeAutoDiscoverURL https://autodiscover-s.outlook.com/autodiscover/autodiscover.svc 
    > ```
    
6.  Farm AD FS: selezionare Usa una **farm AD FS di Windows Server 2012 R2** esistente e immettere il nome del server AD FS.
    
7.  Completare la procedura guidata ed eseguire le convalide necessarie.
    
## <a name="configure-hybrid-connectivity-for-skype-for-business-server"></a>Configurare la connettività ibrida per Skype for Business Server

Seguire le procedure consigliate per la configurazione ibrida di Skype for Business. Per ulteriori informazioni, vedere [Pianificare la connettività ibrida](plan-hybrid-connectivity.md) e Configurare la [connettività ibrida.](configure-hybrid-connectivity.md) 
  
## <a name="configure-hybrid-connectivity-for-exchange-server"></a>Configurare la connettività ibrida per Exchange Server

Se necessario, seguire le procedure consigliate per la configurazione ibrida di Exchange. Per ulteriori informazioni, vedere [Exchange Server Hybrid Deployments.](https://docs.microsoft.com/exchange/exchange-hybrid) 
  
