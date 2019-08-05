---
title: Distribuire una topologia di foresta di risorse
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: Le sezioni seguenti includono indicazioni su come configurare un ambiente con più foreste in un modello di foresta di risorse/utenti per ottenere la funzionalità Skype for business in uno scenario ibrido.
ms.openlocfilehash: 7ef895648c044dc5d1f3f907ad4f75d950a4253a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36185480"
---
# <a name="deploy-a-resource-forest-topology"></a>Distribuire una topologia di foresta di risorse
 
Le sezioni seguenti includono indicazioni su come configurare un ambiente con più foreste in un modello di foresta di risorse/utenti per ottenere la funzionalità Skype for business in uno scenario ibrido. 
  
![Ambiente multiforestale per l'ibrido](../../sfbserver/media/5f079435-b252-4a6a-9638-3577d55b2873.png)
  
## <a name="topology-requirements"></a>Requisiti di topologia

Sono supportate più foreste utente. Tieni presente quanto segue: 
    
- Per le versioni supportate di Lync Server e Skype for Business Server in una configurazione ibrida, vedere Requisiti per la [versione del server](plan-hybrid-connectivity.md#server-version-requirements) in Pianificare la [connettività ibrida tra Skype for Business server e Office 365](plan-hybrid-connectivity.md).
    
- Exchange Server può essere distribuito in uno o più insiemi di strutture, che possono o meno includere la foresta che contiene Skype for Business Server. Verificare di avere applicato l'aggiornamento cumulativo più recente.
    
- Per informazioni dettagliate sulla coesistenza con Exchange Server, inclusi i criteri di supporto e le limitazioni delle varie combinazioni di locale e online, vedere [supporto delle funzionalità](../../sfbserver/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support) in [piano per l'integrazione di Skype for business e Exchange](../../sfbserver/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md).
    
  
## <a name="user-homing-considerations"></a>Considerazioni sui viaggiatori degli utenti

Gli utenti di Skype for business residenti in locale possono avere Exchange homed in locale o online. Gli utenti di Skype for business online dovrebbero usare Exchange Online per un'esperienza ottimale; Tuttavia, questa operazione non è obbligatoria. Exchange in locale non è necessario per implementare Skype for business in entrambi i casi.
  
## <a name="configure-forest-trusts"></a>Configurare i trust tra insiemi di strutture

In una topologia di foresta di risorse, le foreste di risorse che ospitano Skype for Business Server devono considerare attendibili ogni foresta di account che contiene gli account degli utenti che lo accederanno. Se si hanno più foreste di utenti, per abilitare l'autenticazione tra insiemi di strutture è importante che il routing del suffisso del nome sia abilitato per ognuno di questi trust tra insiemi di strutture. Per istruzioni, vedere [gestione dei trust tra insiemi di strutture](https://technet.microsoft.com/en-us/library/cc772440.aspx). Se Exchange Server è distribuito in un'altra foresta e offre funzionalità per gli utenti di Skype for business, lo scambio di hosting della foresta deve considerare attendibile la foresta che ospita Skype for Business Server. Ad esempio, se Exchange è stato distribuito nella foresta dell'account, ciò significherebbe effettivamente un trust bidirezionale tra l'account e le foreste di Skype for business è necessario in tale configurazione.
  
## <a name="synchronize-accounts-into-the-forest-hosting-skype-for-business"></a>Sincronizzare gli account nella foresta che ospita Skype for business

Quando Skype for Business Server è distribuito in un'unica foresta (una foresta di risorse), ma offre funzionalità agli utenti in uno o più altri insiemi di strutture (foreste di account), gli utenti di altre foreste devono essere rappresentati come oggetti utente disabilitati nella foresta in cui Skype for Server aziendale distribuito. Un prodotto di gestione delle identità, ad esempio Microsoft Identity Manager, deve essere distribuito e configurato per eseguire il provisioning e la sincronizzazione degli utenti dalle foreste degli account all'interno della foresta in cui è distribuito Skype for Business Server. Gli utenti devono essere sincronizzati nella foresta che ospita Skype for Business Server come oggetti utente disabilitati. Gli utenti non possono essere sincronizzati come oggetti contatto Active Directory, perché Azure Active Directory Connect non sincronizza correttamente i contatti in Azure AD per l'uso con Skype.
  
Indipendentemente da qualsiasi configurazione a più insiemi di strutture, la foresta che ospita Skype for Business Server può anche creare funzionalità per tutti gli utenti abilitati presenti nella stessa foresta.
  
Per ottenere la sincronizzazione corretta delle identità, è necessario sincronizzare gli attributi seguenti: 
  
|**Foreste degli utenti**|**Foreste di risorse**|
|:-----|:-----|
|attributo del collegamento account scelto  <br/> |attributo del collegamento account scelto  <br/> |
|posta  <br/> |posta  <br/> |
|ProxyAddresses  <br/> |ProxyAddresses  <br/> |
|ObjectSID  <br/> |msRTCSIP-OriginatorSID  <br/> |
   
L' [attributo di collegamento dell'account scelto](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect-design-concepts/) verrà usato come ancoraggio di origine. Se si ha un attributo diverso e non modificabile che si preferisce usare, è possibile farlo; Basta essere sicuri di modificare la regola delle attestazioni ADFS e selezionare l'attributo durante la configurazione di AAD Connect.
  
Non sincronizzare il UPN tra le foreste. Durante i test è stato rilevato che era necessario usare un UPN univoco per ogni foresta utente, perché non è possibile usare lo stesso UPN in più foreste. Di conseguenza, siamo stati presentati con due possibilità, per sincronizzare l'UPN o per non eseguire la sincronizzazione. 
  
- Se l'UPN univoco di ogni foresta utente non è stato sincronizzato con l'oggetto disabilitato associato nella foresta delle risorse, Single Sign-on (SSO) verrebbe interrotto almeno per il tentativo di accesso iniziale (presupponendo che l'utente abbia selezionato l'opzione per salvare la password). Nel client Skype for business supponiamo che i valori SIP/UPN siano gli stessi. Dato che l'indirizzo SIP in questo scenario è user@company.com, ma l'UPN dell'oggetto abilitato nella foresta dell'utente è in realtà user@contoso.company.com, il tentativo di accesso iniziale non riesce e all'utente viene chiesto di immettere le credenziali. Dopo aver immesso il proprio UPN corretto/effettivo, la richiesta di autenticazione verrebbe completata con i controller di dominio nella foresta dell'utente e l'accesso sarebbe riuscito.
    
- Se l'UPN univoco di ogni foresta utente è stato sincronizzato con l'oggetto disabilitato associato nella foresta delle risorse, l'autenticazione ADFS non riuscirà. La regola corrispondente troverebbe l'UPN nell'oggetto nella foresta delle risorse, che era disabilitato e non poteva essere usato per l'autenticazione. 
    
## <a name="create-an-office-365-tenant"></a>Creare un tenant di Office 365

Sarà quindi necessario eseguire il provisioning di un tenant di Office 365 da usare con la distribuzione. Per altre informazioni, vedere [abbonamenti, licenze, account e tenant per le offerte cloud di Microsoft](https://docs.microsoft.com/office365/enterprise/subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings). 
  
## <a name="configure-active-directory-federation-services"></a>Configurare Active Directory Federation Services

Dopo aver installato un tenant, è necessario configurare Active Directory Federation Services (ADFS) in ogni foresta dell'utente. Si presuppone che sia presente un indirizzo SIP e SMTP univoco e un nome dell'entità utente (UPN) per ogni foresta. ADFS è facoltativo e viene usato qui per ottenere Single Sign-on (SSO). DirSync con la sincronizzazione delle password è anche supportato e può essere usato anche al posto di ADFS. 
  
Sono state testate solo distribuzioni con SIP/SMTP e UPN corrispondenti. La mancata corrispondenza di SIP/SMTP/UPN può causare una funzionalità ridotta, ad esempio problemi relativi all'integrazione di Exchange e SSO. 
  
A meno che non si usi un SIP/SMTP/UPN univoco per gli utenti di ogni foresta, è comunque possibile imbattersi in problemi SSO, indipendentemente da dove è distribuito ADFS: 
  
- Trust unidirezionali o bidirezionali tra foreste di risorse/utenti con la farm ADFS distribuita in ogni foresta di utenti, tutti gli utenti condividono il dominio SIP/SMTP comune, ma un UPN univoco per ogni foresta utente. 
    
- Trust bidirezionali tra foreste di risorse/utenti con la farm ADFS distribuita solo nella foresta delle risorse, tutti gli utenti condividono il dominio SIP/SMTP comune, ma un UPN univoco per ogni foresta utente. 
    
Inserendo una farm ADFS in ogni foresta utente e usando un SIP/SMTP/UPN univoco per ogni foresta, risolviamo entrambi i problemi. Durante i tentativi di autenticazione verranno cercati e combinati solo gli account in quella specifica foresta utente. Ciò consentirà di fornire un processo di autenticazione più semplice. 
  
Questa sarà una distribuzione standard di Windows Server 2012 R2 ADFS e dovrebbe funzionare prima di continuare. Per istruzioni, vedere [come installare adfs 2012 R2 per Office 365](https://blogs.technet.com/b/rmilne/archive/2014/04/28/how-to-install-adfs-2012-r2-for-office-365.aspx). 
  
Dopo la distribuzione, è necessario modificare la regola delle attestazioni in base all'ancoraggio di origine selezionato in precedenza. Nella console MMC ADFS, in attendibilità del componente, fare clic con il pulsante destro del mouse su **Microsoft Office 365 Identity Platform**e quindi scegliere **modifica regole attestazione**. Modificare la prima regola e modificare ObjectSID in **EmployeeNumber**. 
  
![Schermata di modifica delle regole con più insiemi di strutture](../../sfbserver/media/f5d485bd-52cc-437f-ba71-217f8902056c.png)
  
## <a name="configure-aad-connect"></a>Configurare la connessione AAD

Nelle topologie della foresta di risorse è necessario che gli attributi utente sia della foresta delle risorse che di qualsiasi foresta di account vengano sincronizzati in Azure AD. Il modo più semplice e consigliato per eseguire questa operazione consiste nell'usare Azure AD Connect per sincronizzare e unire le identità degli utenti di *tutte* le foreste che hanno abilitato gli account utente e la foresta che contiene Skype for business. Per informazioni dettagliate, vedere [configurare Azure ad Connect per Skype for business e teams](configure-azure-ad-connect.md).

Tieni presente che AAD Connect non offre la sincronizzazione nei locali tra l'account e le foreste di risorse. Che devono essere configurate separatamente usando Microsoft Identity Manager o un prodotto simile, come descritto in precedenza.
  
Al termine, quando si unisce AAD Connect, se si guarda un oggetto nel metaverse, dovrebbe essere visualizzato un aspetto simile al seguente: 
  
![Schermata degli oggetti metaverse a più foreste](../../sfbserver/media/16379880-2de3-4c43-b219-1551f5dec5f6.png)
  
Gli attributi evidenziati in verde sono Stati Uniti da Office 365, il giallo si trova nella foresta dell'utente e il colore blu viene dalla foresta delle risorse. 
  
Si tratta di un utente di test e si può notare che AAD Connect ha identificato sourceAnchor e cloudSourceAnchor dall'utente e dagli oggetti della foresta di risorse di Office 365, nel nostro caso 1101, che è il employeeNumber selezionato in precedenza. Fu quindi in grado di unire questo oggetto in quello che vedi sopra. 
  
Per altre informazioni, vedere [integrare le directory locali con Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect/). 
  
La connessione AAD deve essere installata usando le impostazioni predefinite, ad eccezione delle operazioni seguenti: 
  
1. Single Sign-in-con ADFS già distribuito e funzionante: selezionare non **configurare**.
    
2. Connetti le tue directory: Aggiungi tutti i domini.
    
3. Identificare gli utenti nelle directory locali: selezionare le **identità degli utenti esistenti in più directory**e selezionare gli attributi **objectSID** e **msExchangeMasterAccountSID** .
    
4. Identificare gli utenti in Azure AD: Anchor di origine: selezionare l'attributo scelto dopo la lettura [selezionando un buon attributo sourceAnchor](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect-design-concepts/), nome dell'entità utente- **userPrincipalName**.
    
5.  Funzionalità facoltative: selezionare se è stata distribuita la distribuzione ibrida di Exchange.
    
    > [!NOTE]
    >  Se si ha solo Exchange Online, potrebbe verificarsi un problema con gli errori OAuth durante l'individuazione automatica a causa del reindirizzamento CNAME. Per risolvere questo problema, devi impostare l'URL di individuazione automatica di Exchange eseguendo il cmdlet seguente da Skype for Business Server Management Shell:
  
    Set-CsOAuthConfiguration-ExchangeAutoDiscoverURL https://<span>Autodiscover-s.Outlook.com/autodiscover/autodiscover.svc 
    
6.  Farm ADFS: selezionare **Usa una farm di ADFS di Windows Server 2012 R2 esistente** e immettere il nome del server ADFS.
    
7.  Completare la procedura guidata ed eseguire le convalide necessarie.
    
## <a name="configure-hybrid-connectivity-for-skype-for-business-server"></a>Configurare la connettività ibrida per Skype for Business Server

Seguire le procedure consigliate per configurare Skype for business Hybrid. Per altre informazioni, vedere [pianificare la connettività ibrida](plan-hybrid-connectivity.md) e [configurare la connettività ibrida](configure-hybrid-connectivity.md). 
  
## <a name="configure-hybrid-connectivity-for-exchange-server"></a>Configurare la connettività ibrida per Exchange Server

Se necessario, seguire le procedure consigliate per la configurazione di Exchange Hybrid. Per altre informazioni, Vedi [distribuzioni ibride di Exchange Server](https://docs.microsoft.com/en-us/exchange/exchange-hybrid). 
  

