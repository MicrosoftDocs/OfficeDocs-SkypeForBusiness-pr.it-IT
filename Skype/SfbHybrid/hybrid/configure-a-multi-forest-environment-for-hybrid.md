---
title: Distribuzione di una topologia a foresta di risorse
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
description: Nelle sezioni seguenti vengono fornite indicazioni su come configurare un ambiente con più foreste in un modello di foresta di risorse e utenti per fornire le funzionalità di Skype for business in uno scenario ibrido.
ms.openlocfilehash: 33945b245009a221d709e13d587f435aa4c054d8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "41983041"
---
# <a name="deploy-a-resource-forest-topology"></a>Distribuzione di una topologia a foresta di risorse
 
Nelle sezioni seguenti vengono fornite indicazioni su come configurare un ambiente con più foreste in un modello di foresta di risorse e utenti per fornire le funzionalità di Skype for business in uno scenario ibrido. 
  
![Ambiente a più foreste per i sistemi ibridi](../../sfbserver/media/5f079435-b252-4a6a-9638-3577d55b2873.png)
  
## <a name="topology-requirements"></a>Requisiti per la topologia

Sono supportate più foreste di utenti. Tenere presente quanto segue: 
    
- Per le versioni supportate di Lync Server e Skype for Business Server in una configurazione ibrida, vedere [Server Version requirements](plan-hybrid-connectivity.md#server-version-requirements) in [Plan Hybrid connectivity between Skype for Business server e Office 365](plan-hybrid-connectivity.md).
    
- Exchange Server può essere distribuito in una o più foreste, che possono o meno includere la foresta contenente Skype for Business Server. Assicurarsi di aver applicato l'aggiornamento cumulativo più recente.
    
- Per informazioni dettagliate sulla coesistenza con Exchange Server, inclusi i criteri di supporto e le limitazioni nelle diverse combinazioni di locale e online, vedere [funzionalità di supporto](../../sfbserver/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support) in [plan to integre Skype for Business and Exchange](../../sfbserver/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md).
    
  
## <a name="user-homing-considerations"></a>Considerazioni su homing degli utenti

Gli utenti di Skype for business ospitati in locale possono disporre di Exchange in locale o online. Gli utenti di Skype for business online devono utilizzare Exchange Online per un'esperienza ottimale. Tuttavia, non è necessario. Exchange in locale non è necessario per implementare Skype for business in entrambi i casi.
  
## <a name="configure-forest-trusts"></a>Configurare le relazioni di trust tra foreste

In una topologia a foresta di risorse, le foreste di risorse che ospitano Skype for Business Server devono considerare attendibile ogni foresta di account che contiene gli account degli utenti che lo potranno accedere. Se si dispone di più foreste di utenti, per abilitare l'autenticazione tra foreste è importante che il routing dei suffissi del nome sia abilitato per ognuno di questi trust tra foreste. Per istruzioni, vedere [Managing Forest Trusts](https://technet.microsoft.com/library/cc772440.aspx). Se Exchange Server è stato distribuito in un'altra foresta e fornisce funzionalità per gli utenti di Skype for business, la foresta che ospita Exchange deve considerare attendibile la foresta che ospita Skype for Business Server. Ad esempio, se Exchange è stato distribuito nella foresta account, significa che in questa configurazione è necessaria una relazione di trust bidirezionale tra gli account e le foreste di Skype for business.
  
## <a name="synchronize-accounts-into-the-forest-hosting-skype-for-business"></a>Sincronizzare gli account nella foresta che ospita Skype for business

Quando Skype for Business Server viene distribuito in una foresta (una foresta di risorse), ma fornisce funzionalità agli utenti in una o più foreste (foreste di account), gli utenti nelle altre foreste devono essere rappresentati come oggetti utente disabilitati nella foresta in cui Skype for Business Server distribuito. È necessario distribuire e configurare un prodotto di gestione delle identità, ad esempio Microsoft Identity Manager, per eseguire il provisioning e la sincronizzazione degli utenti dalle foreste degli account all'interno della foresta in cui è distribuito Skype for Business Server. Gli utenti devono essere sincronizzati nella foresta che ospita Skype for Business Server come oggetti utente disabilitati. Gli utenti non possono essere sincronizzati come oggetti contatto di Active Directory, perché Azure Active Directory Connect non sincronizza correttamente i contatti in Azure AD per l'utilizzo con Skype.
  
Indipendentemente dalla configurazione di più foreste, la foresta che ospita Skype for Business Server può anche fornire la funzionalità per tutti gli utenti abilitati presenti nella stessa foresta.
  
Per ottenere la sincronizzazione corretta delle identità, è necessario sincronizzare gli attributi seguenti: 
  
|**Foreste di utenti**|**Foreste di risorse**|
|:-----|:-----|
|attributo del collegamento dell'account scelto  <br/> |attributo del collegamento dell'account scelto  <br/> |
|posta elettronica  <br/> |posta elettronica  <br/> |
|ProxyAddresses  <br/> |ProxyAddresses  <br/> |
|Attributo objectSID  <br/> |msRTCSIP-OriginatorSID  <br/> |
   
L' [attributo di collegamento dell'account scelto](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect-design-concepts/) verrà utilizzato come Anchor di origine. Se si dispone di un attributo diverso e immutabile che si preferisce utilizzare, è possibile farlo. Basta essere sicuri di modificare la regola delle attestazioni AD FS e selezionare l'attributo durante la configurazione di AAD Connect.
  
Non sincronizzare la UPN tra le foreste. Durante i test, è stato rilevato che è necessario utilizzare un UPN univoco per ogni foresta utente, in quanto non è possibile utilizzare lo stesso UPN tra più foreste. Di conseguenza, sono state presentate due possibilità, per sincronizzare l'UPN o per non eseguire la sincronizzazione. 
  
- Se l'UPN univoco di ogni foresta utente non è stato sincronizzato con l'oggetto disabilitato associato nella foresta di risorse, il servizio Single Sign-on (SSO) verrebbe interrotto almeno per il tentativo di accesso iniziale (presupponendo che l'utente abbia selezionato l'opzione per salvare la password). Nel client Skype for business, si presuppone che i valori SIP/UPN siano identici. Poiché l'indirizzo SIP in questo scenario è user@company.com, ma l'UPN dell'oggetto abilitato nella foresta utente è in realtà user@contoso.company.com, il tentativo di accesso iniziale verrebbe a mancare e all'utente verrà richiesto di immettere le credenziali. Dopo aver immesso il rispettivo UPN corretto/effettivo, la richiesta di autenticazione verrebbe completata rispetto ai controller di dominio nella foresta di utenti e l'accesso avrebbe avuto esito positivo.
    
- Se l'UPN univoco di ogni foresta utente è stato sincronizzato con l'oggetto disabilitato associato nella foresta di risorse, l'autenticazione AD FS avrà esito negativo. La regola di corrispondenza troverebbe l'UPN nell'oggetto nella foresta di risorse, che era disabilitato e non poteva essere utilizzato per l'autenticazione. 
    
## <a name="create-an-office-365-tenant"></a>Creare un tenant di Office 365

Sarà quindi necessario eseguire il provisioning di un tenant di Office 365 da utilizzare con la distribuzione. Per ulteriori informazioni, vedere [abbonamenti, licenze, account e tenant per offerte cloud di Microsoft](https://docs.microsoft.com/office365/enterprise/subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings). 
  
## <a name="configure-active-directory-federation-services"></a>Configurazione di Active Directory Federation Services

Una volta che si dispone di un tenant, è necessario configurare Active Directory Federation Services (ADFS) in ognuna delle foreste degli utenti. Si presuppone che l'indirizzo SIP e SMTP e il nome dell'entità utente (UPN) di ogni foresta siano univoci. AD FS è facoltativo e viene utilizzato qui per ottenere Single Sign-on (SSO). DirSync con sincronizzazione password è supportato anche e può essere utilizzato anche al posto di ADFS. 
  
Sono state testate solo le distribuzioni con SIP/SMTP e UPN corrispondenti. Se non si dispone di SIP/SMTP/UPN corrispondente, potrebbero verificarsi funzionalità ridotte, ad esempio problemi relativi all'integrazione di Exchange e SSO. 
  
A meno che non si utilizzi un SIP/SMTP/UPN univoco per gli utenti di ogni foresta, è comunque possibile eseguire problemi SSO, indipendentemente dalla distribuzione di ADFS: 
  
- Attendibilità unidirezionale o bidirezionale tra foreste di risorse e utenti con farm ADFS distribuita in ogni foresta di utenti, tutti gli utenti condividono un dominio SIP/SMTP comune ma un UPN univoco per ogni foresta utente. 
    
- Trust bidirezionali tra foreste di risorse e utenti con farm ADFS distribuita solo nella foresta di risorse, tutti gli utenti condividono il dominio SIP/SMTP comune ma il nome UPN univoco per ogni foresta utente. 
    
Se si dispone di una farm ADFS in ogni foresta di utenti e si utilizza un SIP/SMTP/UPN univoco per ogni foresta, vengono risolti entrambi i problemi. Durante i tentativi di autenticazione vengono ricercati e confrontati solo gli account nella foresta di utenti specifica. Ciò consentirà di fornire un processo di autenticazione più semplice. 
  
Questa sarà una distribuzione standard di Windows Server 2012 R2 AD FS e dovrebbe funzionare prima di continuare. Per istruzioni, vedere [How to install ad FS 2012 R2 for Office 365](https://blogs.technet.com/b/rmilne/archive/2014/04/28/how-to-install-adfs-2012-r2-for-office-365.aspx). 
  
Dopo la distribuzione, è necessario modificare la regola delle attestazioni in modo che corrisponda all'ancoraggio di origine selezionato in precedenza. Nella console MMC ADFS, sotto Trust relying party, fare clic con il pulsante destro del mouse su **Microsoft Office 365 Identity Platform**e quindi scegliere **modifica regole attestazione**. Modificare la prima regola e cambiare attributo objectSID in **EmployeeNumber**. 
  
![Schermata di modifica delle regole a più foreste](../../sfbserver/media/f5d485bd-52cc-437f-ba71-217f8902056c.png)
  
## <a name="configure-aad-connect"></a>Configurazione di AAD Connect

Nelle topologie a foresta di risorse, è necessario che gli attributi degli utenti sia dalla foresta di risorse che da qualsiasi foresta di account siano sincronizzati in Azure AD. Il metodo più semplice e consigliato per eseguire questa operazione consiste nell'eseguire la sincronizzazione di Azure AD Connect e unire le identità degli utenti da *tutte* le foreste che hanno abilitato gli account utente e la foresta che contiene Skype for business. Per ulteriori informazioni, vedere [configurare Azure ad Connect per Skype for business e teams](configure-azure-ad-connect.md).

Si noti che AAD Connect non fornisce la sincronizzazione nei locali tra l'account e le foreste di risorse. Che devono essere configurati separatamente utilizzando Microsoft Identity Manager o un prodotto simile, come descritto in precedenza.
  
Al termine dell'operazione e l'Unione di AAD Connect, se si esamina un oggetto nel metaverse, dovrebbe essere visualizzato qualcosa di simile al seguente: 
  
![Schermata oggetto metaverse a più foreste](../../sfbserver/media/16379880-2de3-4c43-b219-1551f5dec5f6.png)
  
Gli attributi evidenziati in verde sono Stati Uniti da Office 365, i gialli sono dalla foresta degli utenti e quelli blu sono dalla foresta di risorse. 
  
Si tratta di un utente di testing e si può vedere che AAD Connect ha identificato sourceAnchor e cloudSourceAnchor dall'utente e dagli oggetti della foresta di risorse da Office 365, nel nostro caso 1101, che è la employeeNumber selezionata in precedenza. È stato quindi in grado di unire questo oggetto in quello che si vede sopra. 
  
Per ulteriori informazioni, vedere [integrazione delle directory locali con Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect/). 
  
L'installazione di AAD Connect deve essere eseguita utilizzando le impostazioni predefinite, ad eccezione delle operazioni seguenti: 
  
1. Single Sign-in-con ADFS già distribuito e funzionante: selezionare non **configurare**.
    
2. Connettere le directory: aggiungere tutti i domini.
    
3. Identificare gli utenti nelle directory locali: selezionare **identità utente esistenti tra più directory**e selezionare gli attributi **attributo objectSID** e **msExchangeMasterAccountSID** .
    
4. Identificare gli utenti in Azure AD: Anchor di origine: selezionare l'attributo che si è scelto dopo la lettura [selezionando un attributo sourceAnchor valido](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect-design-concepts/), nome dell'entità utente- **userPrincipalName**.
    
5.  Funzionalità facoltative: selezionare se è stata distribuita la distribuzione ibrida di Exchange.
    
    > [!NOTE]
    >  Se si dispone solo di Exchange Online, è possibile che si verifichi un problema con gli errori OAuth durante l'individuazione automatica a causa del reindirizzamento CNAME. Per risolvere questo errore, è necessario impostare l'URL di individuazione automatica di Exchange eseguendo il cmdlet seguente da Skype for Business Server Management Shell:
  
    Set-CsOAuthConfiguration-ExchangeAutoDiscoverURL https://<span>Autodiscover-s.Outlook.com/autodiscover/autodiscover.svc 
    
6.  Farm ADFS: selezionare **Usa una farm di Windows Server 2012 R2 ad FS esistente** e immettere il nome del server ad FS.
    
7.  Completare la procedura guidata ed eseguire le convalide necessarie.
    
## <a name="configure-hybrid-connectivity-for-skype-for-business-server"></a>Configurare la connettività ibrida per Skype for Business Server

Seguire le procedure consigliate per la configurazione dell'ambiente ibrido di Skype for business. Per ulteriori informazioni, vedere [pianificare la connettività ibrida](plan-hybrid-connectivity.md) e [configurare la connettività ibrida](configure-hybrid-connectivity.md). 
  
## <a name="configure-hybrid-connectivity-for-exchange-server"></a>Configurare la connettività ibrida per Exchange Server

Se necessario, seguire le procedure consigliate per la configurazione dell'ambiente ibrido di Exchange. Per ulteriori informazioni, vedere [distribuzioni ibride di Exchange Server](https://docs.microsoft.com/exchange/exchange-hybrid). 
  

