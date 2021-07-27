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
description: Nelle sezioni seguenti vengono fornite indicazioni su come configurare un ambiente con più foreste in un modello di foresta risorsa/utente per fornire Skype for Business funzionalità in uno scenario ibrido.
ms.openlocfilehash: 38e41a2ae845120bbdc49419d47b264f69c0a5fe
ms.sourcegitcommit: 9879bc587382755d9a5cd63a75b0e7dc4e15574c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/21/2021
ms.locfileid: "53510697"
---
# <a name="deploy-a-resource-forest-topology"></a>Distribuire una topologia di foresta di risorse

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

 
Nelle sezioni seguenti vengono fornite indicazioni su come configurare un ambiente con più foreste in un modello di foresta risorsa/utente per fornire Skype for Business funzionalità in uno scenario ibrido. 
  
![Ambiente a più foreste per ambienti ibridi](../../sfbserver/media/5f079435-b252-4a6a-9638-3577d55b2873.png)
  
## <a name="topology-requirements"></a>Requisiti per la topologia

Sono supportate più foreste utente. Tenere presente quanto segue: 
    
- Per le versioni supportate di Lync Server e Skype for Business Server in una configurazione ibrida, vedere [Server version requirements](plan-hybrid-connectivity.md#server-version-requirements) in Plan hybrid connectivity between Skype for Business Server and Microsoft 365 or [Office 365](plan-hybrid-connectivity.md).
    
- Exchange Server possono essere distribuiti in una o più foreste, che possono includere o meno la foresta contenente Skype for Business Server. Assicurati di aver applicato l'aggiornamento cumulativo più recente.
    
- Per informazioni dettagliate sulla coesistenza con Exchange Server, inclusi i criteri di supporto e le limitazioni in varie combinazioni di locale e online, vedere [Supporto](../../sfbserver/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support) delle funzionalità in [Plan to integrate Skype for Business and Exchange](../../sfbserver/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md).
    
  
## <a name="user-homing-considerations"></a>Considerazioni sull'homing degli utenti

Skype for Business gli utenti ospitati in locale possono Exchange ospitati in locale o online. Skype for Business Gli utenti online devono usare Exchange Online per un'esperienza ottimale; Tuttavia, questa operazione non è necessaria. Exchange locale non è necessario implementare Skype for Business in entrambi i casi.
  
## <a name="configure-forest-trusts"></a>Configurare trust tra foreste

In una topologia di foresta di risorse, le foreste di risorse che ospitano Skype for Business Server devono considerare attendibile ogni foresta di account contenente gli account degli utenti che vi accederanno. Se si dispone di più foreste utente, per abilitare l'autenticazione tra foreste è importante che il routing dei suffissi dei nomi sia abilitato per ognuno di questi trust tra foreste. Per istruzioni, vedere [Managing Forest Trusts.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc772440(v=ws.11)) Se è stata Exchange Server distribuita in un'altra foresta e fornisce funzionalità per gli utenti Skype for Business, la foresta che ospita Exchange deve considerare attendibile la foresta che ospita Skype for Business Server. Ad esempio, se Exchange sono stati distribuiti nella foresta di account, in questa configurazione è effettivamente necessario un trust bidirezionale tra account e Skype for Business foreste.
  
## <a name="synchronize-accounts-into-the-forest-hosting-skype-for-business"></a>Sincronizzare gli account nella foresta che ospita Skype for Business

Quando Skype for Business Server viene distribuito in una foresta (una foresta di risorse), ma fornisce funzionalità agli utenti in una o più altre foreste (foreste account), gli utenti nelle altre foreste devono essere rappresentati come oggetti utente disabilitati nella foresta in cui viene distribuito Skype for Business Server. Un prodotto di gestione delle identità, ad esempio Microsoft Identity Manager, deve essere distribuito e configurato per effettuare il provisioning e sincronizzare gli utenti dalle foreste di account nella foresta in cui Skype for Business Server viene distribuito. Gli utenti devono essere sincronizzati nella foresta che ospita Skype for Business Server come oggetti utente disabilitati. Gli utenti non possono essere sincronizzati come oggetti contatto di Active Directory, perché Azure Active Directory Connessione i contatti non verranno sincronizzati correttamente in Azure AD per l'utilizzo con Skype.
  
Indipendentemente da qualsiasi configurazione a più foreste, la foresta che ospita Skype for Business Server può inoltre fornire funzionalità per tutti gli utenti abilitati presenti nella stessa foresta.
  
Per ottenere una corretta sincronizzazione delle identità, è necessario sincronizzare gli attributi seguenti: 
  
|**Foreste utente**|**Foreste di risorse**|
|:-----|:-----|
|attributo di collegamento account scelto  <br/> |attributo di collegamento account scelto  <br/> |
|posta elettronica  <br/> |posta elettronica  <br/> |
|ProxyAddresses  <br/> |ProxyAddresses  <br/> |
|ObjectSID  <br/> |msRTCSIP-OriginatorSID  <br/> |
   
[L'attributo di collegamento account](/azure/active-directory/hybrid/plan-connect-design-concepts) scelto verrà utilizzato come ancoraggio di origine. Se si dispone di un attributo diverso e non modificabile che si preferisce utilizzare, è possibile farlo. è sufficiente assicurarsi di modificare la regola delle attestazioni di AD FS e selezionare l'attributo durante la configurazione Connessione AAD.
  
Non sincronizzare gli UPN tra le foreste. Durante i test è stato rilevato che era necessario utilizzare un UPN univoco per ogni foresta utente, poiché non è possibile utilizzare lo stesso UPN in più foreste. Di conseguenza, sono state presentate due possibilità, per sincronizzare l'UPN o per non eseguire la sincronizzazione. 
  
- Se l'UPN univoco di ogni foresta utente non è stato sincronizzato con l'oggetto disabilitato associato nella foresta di risorse, single sign-on (SSO) verrà interrotto almeno per il tentativo di accesso iniziale (presupponendo che l'utente abbia selezionato l'opzione per salvare la password). Nel client Skype for Business, si presuppone che i valori SIP/UPN siano gli stessi. Poiché l'indirizzo SIP in questo scenario è user@company.com, ma l'UPN dell'oggetto abilitato nella foresta utente è in realtà user@contoso.company.com, il tentativo di accesso iniziale avrà esito negativo e all'utente verrà richiesto di immettere le credenziali. Dopo aver immesso l'UPN corretto/effettivo, la richiesta di autenticazione verrà completata nei controller di dominio nella foresta utenti e l'accesso verrà eseguito correttamente.
    
- Se l'UPN univoco di ogni foresta utente è stato sincronizzato con l'oggetto disabilitato associato nella foresta di risorse, l'autenticazione AD FS avrà esito negativo. La regola di corrispondenza trova l'UPN dell'oggetto nella foresta di risorse, che è stato disabilitato e non è stato possibile utilizzare per l'autenticazione. 
    
## <a name="create-a-microsoft-365-or-office-365-organization"></a>Creare un'Microsoft 365 o Office 365 organizzazione

Sarà quindi necessario effettuare il provisioning di Microsoft 365 o Office 365 per l'utilizzo con la distribuzione. Per ulteriori informazioni, vedere [Sottoscrizioni, licenze, account](/office365/enterprise/subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings)e tenant per le offerte cloud di Microsoft. 
  
## <a name="configure-active-directory-federation-services"></a>Configurare Active Directory Federation Services

Dopo aver creato un tenant, sarà necessario configurare Active Directory Federation Services (AD FS) in ogni foresta utente. Si presuppone che sia presente un indirizzo SIP e SMTP univoco e un nome dell'entità utente (UPN) per ogni foresta. ADFS è facoltativo e viene usato qui per ottenere single sign-on (SSO). È supportato anche DirSync con sincronizzazione password e può essere utilizzato al posto di ADFS. 
  
Sono state testate solo le distribuzioni con SIP/SMTP e UPN corrispondenti. La presenza di SIP/SMTP/UPN corrispondenti può comportare funzionalità ridotte, ad esempio problemi con l'integrazione Exchange SSO. 
  
A meno che non si utilizzi un SIP/SMTP/UPN univoco per gli utenti di ogni foresta, è comunque possibile che si verificano problemi SSO, indipendentemente dalla posizione di distribuzione di ADFS: 
  
- Trust unidirezionale o bidirezionale tra foreste di risorse/utenti con farm ADFS distribuita in ogni foresta utente, tutti gli utenti condividono un dominio SIP/SMTP comune ma un UPN univoco per ogni foresta utente. 
    
- Trust bidirezionale tra foreste di risorse/utenti con farm AD FS distribuita solo nella foresta di risorse, tutti gli utenti condividono un dominio SIP/SMTP comune ma un UPN univoco per ogni foresta utente. 
    
Inserendo una farm AD FS in ogni foresta utente e utilizzando un SIP/SMTP/UPN univoco per ogni foresta, vengono risolti entrambi i problemi. Solo gli account in quella foresta utente specifica verranno cercati e corrispondenti durante i tentativi di autenticazione. In questo modo sarà possibile garantire un processo di autenticazione più semplice. 
  
Si tratta di una distribuzione standard di AD FS Windows Server 2012 R2 e dovrebbe funzionare prima di continuare. Per istruzioni, vedere [How to Install AD FS 2012 R2 For Microsoft 365 or Office 365](https://blogs.technet.com/b/rmilne/archive/2014/04/28/how-to-install-adfs-2012-r2-for-office-365.aspx). 
  
Dopo la distribuzione, è necessario modificare la regola delle attestazioni in modo che corrisponda all'ancoraggio di origine selezionato in precedenza. Nella mmc AD FS, in Attendibilità componente, fare clic con il pulsante destro del mouse su **Microsoft 365 Identity Platform** o Microsoft Office 365 Identity **Platform** e quindi scegliere Modifica regole **attestazione.** Modificare la prima regola e ObjectSID in **employeeNumber**. 
  
![Schermata Modifica regole a più foreste](../../sfbserver/media/f5d485bd-52cc-437f-ba71-217f8902056c.png)
  
## <a name="configure-aad-connect"></a>Configurare AAD Connessione

Nelle topologie di foresta di risorse, è necessario che gli attributi utente della foresta di risorse e di tutte le foreste di account siano sincronizzati in Azure AD. Il modo più semplice e consigliato per eseguire questa operazione è sincronizzare  e unire le identità utente di Azure AD Connessione da tutte le foreste che hanno abilitato gli account utente e la foresta che contiene Skype for Business. Per informazioni dettagliate, [vedere Configure Azure AD Connessione for Skype for Business and Teams](configure-azure-ad-connect.md).

Tenere presente che AAD Connessione non fornisce la sincronizzazione locale tra le foreste di account e risorse. Che deve essere configurato separatamente utilizzando Microsoft Identity Manager o un prodotto simile, come descritto in precedenza.
  
Al termine dell'unione Connessione AAD, se si osserva un oggetto nel metaverse, si dovrebbe vedere qualcosa di simile al seguente: 
  
![Schermata dell'oggetto Metaverse a più foreste](../../sfbserver/media/16379880-2de3-4c43-b219-1551f5dec5f6.png)
  
Gli attributi evidenziati in verde sono stati uniti da Microsoft 365 o Office 365, il giallo deriva dalla foresta utente e il blu dalla foresta di risorse. 
  
Si tratta di un utente di test e si può vedere che AAD Connessione ha identificato sourceAnchor e cloudSourceAnchor dall'utente e gli oggetti foresta di risorse da Microsoft 365 o Office 365, nel nostro caso 1101, che è il employeeNumber selezionato in precedenza. È stato quindi possibile unire questo oggetto a quello visualizzato in precedenza. 
  
Per ulteriori informazioni, vedere Integrare le directory [locali con Azure Active Directory](/azure/active-directory/hybrid/whatis-hybrid-identity). 
  
AAD Connessione deve essere installato utilizzando le impostazioni predefinite, ad eccezione dei seguenti: 
  
1. Single #A0 - Con ADFS già distribuito e funzionante: selezionare **Non configurare**.
    
2. Connessione directory: aggiungere tutti i domini.
    
3. Identificare gli utenti nelle directory locali: selezionare Le identità utente esistono in più **directory** e selezionare gli attributi **ObjectSID** e **msExchangeMasterAccountSID.**
    
4. Identificare gli utenti in Azure AD: ancoraggio origine: selezionare l'attributo scelto dopo aver letto Selezione di un attributo [sourceAnchor](/azure/active-directory/hybrid/plan-connect-design-concepts#selecting-a-good-sourceanchor-attribute)valido, Nome entità utente - **userPrincipalName**.
    
5.  Funzionalità facoltative: selezionare se è stata Exchange distribuzione ibrida.
    
    > [!NOTE]
    >  Se si dispone solo di Exchange Online, potrebbe verificarsi un problema con errori OAuth durante l'individuazione automatica a causa del reindirizzamento CNAME. Per risolvere il problema, è necessario impostare l'URL di individuazione automatica Exchange eseguendo il cmdlet seguente da Skype for Business Server Management Shell:
    >
    > ```powershell
    > Set-CsOAuthConfiguration -ExchangeAutoDiscoverURL https://autodiscover-s.outlook.com/autodiscover/autodiscover.svc 
    > ```
    
6.  Farm AD FS: selezionare **Usa una farm AD FS Windows Server 2012 R2** esistente e immettere il nome del server AD FS.
    
7.  Completare la procedura guidata ed eseguire le convalide necessarie.
    
## <a name="configure-hybrid-connectivity-for-skype-for-business-server"></a>Configurare la connettività ibrida per Skype for Business Server

Seguire le procedure consigliate per la configurazione Skype for Business ibrida. Per ulteriori informazioni, vedere [Plan hybrid connectivity](plan-hybrid-connectivity.md) e Configure hybrid [connectivity](configure-hybrid-connectivity.md). 
  
## <a name="configure-hybrid-connectivity-for-exchange-server"></a>Configurare la connettività ibrida per Exchange Server

Se necessario, seguire le procedure consigliate per la configurazione Exchange ibrida. Per ulteriori informazioni, vedere [Exchange Server Hybrid Deployments](/exchange/exchange-hybrid). 
