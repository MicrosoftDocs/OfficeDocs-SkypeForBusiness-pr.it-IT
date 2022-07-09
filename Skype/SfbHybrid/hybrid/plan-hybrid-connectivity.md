---
title: Pianificare la connettività ibrida | Skype for Business Server e Teams
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
search.appverid: MET150
description: Pianificare l'implementazione della connettività ibrida tra Skype for Business Server e Teams configurando Skype for Business modalità ibrida.
ms.custom: seo-marvel-jun2020
ms.openlocfilehash: a73b14a3642a216ff9cbbe919b586979aabf6a81
ms.sourcegitcommit: 15ec17eff4ad4c962d00b8683513f9b269d82917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2022
ms.locfileid: "66695049"
---
# <a name="plan-hybrid-connectivity-between-skype-for-business-server-and-teams"></a>Pianificare la connettività ibrida tra Skype for Business Server e Teams

> [!Important]
> Anche se Skype for Business Online è stato ritirato dal 2021, i prodotti locali Skype for Business Server 2019, Skype for Business Server 2015 e Lync Server 2013 sono ancora supportati. Microsoft supporta inoltre ambienti ibridi tra questi prodotti locali e Microsoft Teams. Ciò consente alle organizzazioni con queste distribuzioni locali di eseguire la migrazione degli utenti a TeamsOnly.  Infine, Cloud Connector Edition di Skype for Business Server non è più supportato. I clienti che richiedono la connettività PSTN locale devono usare [l'instradamento diretto](/MicrosoftTeams/direct-routing-landing-page).


Leggere questo argomento per informazioni su come pianificare la connettività ibrida tra Skype for Business Server o Lync Server 2013 e Teams. La configurazione della connettività ibrida è il primo passaggio per spostare l'ambiente locale verso un ambiente solo di Microsoft Teams nel cloud.

In una distribuzione locale di Skype for Business Server, anche gli utenti di Skype for Business possono usare Teams, ma non tutte le funzionalità di Teams sono disponibili per tali utenti purché siano configurati per l'uso della distribuzione Skype for Business Server locale. Si dice che questi utenti siano "ospitati" in locale e alcune funzionalità di Teams non sono disponibili mentre questi utenti sono ospitati in locale, ad esempio:

- Le chiamate federate e le chat tramite il client Teams dell'utente con utenti di altre organizzazioni non sono disponibili
- Comunicazione di interoperabilità tramite il client Teams dell'utente con altri utenti dell'organizzazione che usano Skype for Business client.
- Funzionalità di chiamata PSTN (se all'utente viene assegnata una licenza di sistema telefonico).

Per ottenere funzionalità complete di Teams, questi utenti devono essere spostati da Skype for Business locale al cloud, a quel punto l'utente diventa TeamsOnly. L'atto di spostare un utente dall'ambiente locale al cloud imposterà la modalità di coesistenza dell'utente su TeamsOnly. Dopo lo spostamento degli utenti nel cloud e in TeamsOnly, tutte le chat e le chiamate in arrivo vengono spostate nel client teams (a differenza dell'uso side-by-side di Teams).  Per altre informazioni, vedere Linee guida sulla [coesistenza di Teams con Skype for Business e migrazione](/microsoftteams/coexistence-chat-calls-presence) e [interoperabilità per le organizzazioni che usano Teams insieme a Skype for Business](/microsoftteams/migration-interop-guidance-for-teams-with-skype).

Lo spostamento degli utenti tra l'ambiente locale e TeamsOnly nel cloud richiede la configurazione Skype for Business modalità ibrida. Inoltre, prima di rimuovere la distribuzione locale Skype for Business spostare tutti gli utenti dall'ambiente locale al cloud.   Dopo aver configurato la connettività ibrida, è possibile spostare gli utenti nel cloud in base alla pianificazione e alle esigenze aziendali.  Grazie al routing diretto è possibile sfruttare l'infrastruttura vocale locale durante lo spostamento nel cloud e dopo il completamento della migrazione.

Questo argomento descrive i requisiti di infrastruttura e sistema necessari per configurare la connettività ibrida tra la distribuzione locale Skype for Business Server esistente e Teams.

Dopo aver letto questo argomento e aver configurato la connettività ibrida, vedere [Configurare la connettività ibrida tra Skype for Business Server e Teams](configure-hybrid-connectivity.md). Gli argomenti di configurazione forniscono indicazioni dettagliate per la configurazione della connettività ibrida tra la distribuzione locale e Teams.


## <a name="implications-of-the-retirement-of-skype-for-business-online"></a>Implicazioni del ritiro di Skype for Business Online
È importante ricordare che sia prima che dopo il ritiro di Skype for Business Online, gli utenti ospitati in Skype for Business Server locale possono usare Teams, ma non possono essere TeamsOnly. Per impostazione predefinita, gli utenti locali sono in modalità Isole e vengono assegnati a qualsiasi modalità diversa da TeamsOnly. Gli utenti possono sperimentare tutti i vantaggi di Teams, in particolare la federazione, il supporto PSTN e la garanzia che tutte le chat e le chiamate in ingresso atterrano in Teams, una volta che sono in modalità TeamsOnly. 

Il ritiro di Skype for Business Online non influisce sul ciclo di vita del supporto esistente di Skype for Business Server o Lync Server 2013.  Tuttavia, il ritiro di Skype for Business Online ha avuto un impatto su alcuni aspetti del **modo** in *cui gli utenti passano al cloud e diventano TeamsOnly* nelle organizzazioni con Skype for Business Server locale o Lync Server 2013, incluse le organizzazioni ibride esistenti. L'uso dell'ambiente ibrido come configurazione preliminare per la transizione dall'ambiente locale al cloud (ad esempio TeamsOnly) rimane invariato.

Prima del ritiro di Skype for Business Online, le organizzazioni ibride possono essere costituite da tre tipi di utenti di base: 
- Utenti locali (che possono o meno usare Teams, ma non solo in modalità Teams) 
- Utenti online con qualsiasi modalità di coesistenza diversa da TeamsOnly
- TeamsSolo utenti.

Dopo il ritiro di Skype for Business Online, tuttavia, le organizzazioni ibride possono essere costituite solo da due tipi di utenti di base: 
- Utenti locali (che possono o meno usare Teams, ma non in modalità TeamsOnly)
- Solo utenti di Teams. 

Per consentire alle organizzazioni di passare da Skype for Business Server o Lync Server 2013 a Teams, devono comunque configurare e configurare l'ambiente ibrido usando lo stesso set di strumenti, *esattamente come prima del ritiro*. Quando si sposta un utente dall'ambiente locale a TeamsOnly, non è più necessario specificare l'opzione `-MoveToTeams` in `Move-CsUser`. In precedenza, se questa opzione non veniva specificata, gli utenti passavano dalla home page in Skype for Business Server locale a Skype for Business Online e la modalità rimaneva invariata. Tuttavia, poiché Skype Business Online è stato ritirato, lo spostamento di un utente dall'ambiente locale al cloud con `Move-CsUser` assegnerà *automaticamente* la modalità TeamsOnly e avvierà la conversione delle riunioni dall'ambiente locale alle riunioni di Teams, indipendentemente dal fatto che il `-MoveToTeams` commutatore sia specificato. Ciò significa anche che le organizzazioni con Lync Server 2013, che non hanno mai avuto il `MoveToTeams` commutatore, possono spostare gli utenti direttamente in TeamsOnly dall'ambiente locale. 

Analogamente, se un nuovo utente viene creato direttamente in Microsoft 365 anziché in locale, l'utente avrà automaticamente la modalità Solo Teams indipendentemente dalla modalità del tenant. Tenere presente che in un'organizzazione ibrida con almeno un utente locale devono essere creati nuovi utenti nel Active Directory locale (e quindi sincronizzati in Microsoft 365), anziché creare direttamente un utente in Microsoft 365, per garantire che gli utenti locali possano instradarsi al nuovo utente *anche se si intende che il nuovo utente sia un utente cloud*. Una volta creati nella directory locale, questi nuovi utenti devono essere abilitati per *sip nella* distribuzione Skype for Business locale e quindi, se lo si desidera, spostati nel cloud per diventare TeamsOnly. 

Le modalità di coesistenza continuano a esistere dopo il ritiro di Skype for Business Online. Come in precedenza, agli utenti con account ospitati in Skype for Business Server locale può essere assegnata qualsiasi modalità di coesistenza tranne TeamsOnly. Dopo il ritiro, tuttavia, gli utenti ospitati online possono essere solo TeamsOnly. Non è più possibile assegnare una modalità diversa da TeamsOnly a un utente che è disponibile online.


> [!Important]
> Le organizzazioni ibride esistenti con utenti ospitati in Skype for Business Online che non sono TeamsOnly devono concentrarsi sull'aggiornamento di questi utenti alla modalità Solo Teams il prima possibile. Se l'organizzazione ha ancora utenti ospitati in Skype for Business *Online* che non sono TeamsOnly, verrà pianificato un aggiornamento assistito da Microsoft per la transizione di questi utenti a TeamsOnly. **Gli aggiornamenti assistiti da Microsoft non influiranno sugli utenti ospitati in Skype for Business Server locale.** Le notifiche di pianificazione verranno inviate in anticipo ai clienti ibridi con utenti ospitati in Skype for Business Online prima che questi utenti online, non Solo Teams, vengano aggiornati a Teams.

## <a name="about-shared-sip-address-space-functionality"></a>Informazioni sulla funzionalità Spazio indirizzi SIP condiviso

<a name="BKMK_Overview"> </a>

Con la connettività ibrida configurata tra una distribuzione locale di Skype for Business Server e Teams, è possibile avere alcuni utenti ospitati in locale e alcuni utenti ospitati online.

Questo tipo di configurazione si basa sulla funzionalità dello spazio indirizzi SIP condiviso ed è talvolta definito "dominio diviso", ovvero gli utenti di un dominio, ad esempio contoso.com, vengono divisi tra l'uso di Skype for Business Server in locale e Teams, come illustrato nel diagramma seguente:

![Skype for Business Hybrid connettività- split domain.](../../sfbserver2019/media/plan-hybrid-connectivity-2019-1.png)

Quando lo spazio indirizzi SIP condiviso è configurato:

- Azure Active Directory Connect viene usato per sincronizzare la directory locale con Microsoft 365.
- Gli utenti ospitati in locale interagiscono con i server Skype for Business locali.
- Gli utenti ospitati online interagiscono con Teams.
- Gli utenti di entrambi gli ambienti possono comunicare tra loro.
- Il Active Directory locale è autorevole. Tutti gli utenti devono prima essere creati nel Active Directory locale e quindi sincronizzati con Azure AD. Anche se si prevede che l'utente sia disponibile online, è necessario prima creare l'utente nell'ambiente locale e quindi spostarlo online per assicurarsi che l'utente sia individuabile dagli utenti locali.

Prima che un utente possa essere spostato online, all'utente deve essere assegnata una licenza di Teams e Skype for Business Online (piano 2). **L'assegnazione della licenza Skype for Business Online è necessaria anche dopo il ritiro di Skype for Business Online.** Se gli utenti vogliono sfruttare le funzionalità online aggiuntive, ad esempio Audioconferenza o Sistema telefonico, è necessario assegnare loro la licenza appropriata in Microsoft 365.

## <a name="hybrid-connectivity-infrastructure-requirements"></a>Requisiti dell'infrastruttura di connettività ibrida

<a name="BKMK_Infrastructure"> </a>

Per implementare la connettività ibrida tra l'ambiente locale e i servizi di comunicazione microsoft 365, è necessario soddisfare i requisiti dell'infrastruttura seguenti:

- Una singola distribuzione locale di Skype for Business Server o Lync Server distribuita in una topologia supportata. Vedere [Requisiti della topologia](plan-hybrid-connectivity.md#BKMK_Topology) in questo argomento.

- Un'organizzazione di Microsoft 365 con Teams.
    > [!NOTE]
    > È possibile usare un solo tenant per una configurazione ibrida con la distribuzione locale.
    
- Azure Active Directory Connect per sincronizzare la directory locale con Microsoft 365. Per altre informazioni vedere [Azure AD Connect: account e autorizzazioni](/azure/active-directory/connect/active-directory-aadconnect-accounts-permissions).

- Skype for Business Server strumenti di amministrazione. Questi sono necessari per spostare gli utenti dall'ambiente locale al cloud. Questi strumenti devono essere installati in un server con accesso sia alla distribuzione locale che a Internet.
- Strumenti di amministrazione online. È possibile usare l'interfaccia di amministrazione di Teams o Windows PowerShell per gestire Teams. Per usare PowerShell per gestire Teams, scaricare e installare il modulo PowerShell di Teams. Il connettore online Skype for Business è stato ritirato.
- È necessario abilitare lo spazio indirizzi SIP condiviso e la distribuzione locale deve essere configurata per l'uso di Microsoft 365 come provider di hosting. Per altre informazioni sui passaggi necessari per configurare la connettività ibrida, vedere [Configurare la connettività ibrida](configure-hybrid-connectivity.md).

Dopo aver configurato la connettività ibrida, è possibile spostare gli utenti in Teams. Per altre informazioni, vedere [Spostare gli utenti dall'ambiente locale a Teams](move-users-from-on-premises-to-teams.md).

## <a name="server-version-requirements"></a>Requisiti per la versione del server

<a name="BKMK_Topology"> </a>

Per configurare la distribuzione ibrida con **Teams**, è necessario avere una delle topologie supportate seguenti:

- Distribuzione di Skype for Business Server 2019 con tutti i server che eseguono Skype for Business Server 2019.
- Distribuzione di Skype for Business Server 2015 con tutti i server che eseguono Skype for Business Server 2015.
- Una distribuzione di Lync Server 2013 in cui tutti i server eseguono Lync Server 2013.  Tuttavia, se è necessaria la connettività vocale ibrida, è necessario usare una topologia di versione mista, come indicato di seguito.
- Una distribuzione con un massimo di 2 diverse versioni del server, come indicato di seguito:
  - Skype for Business Server 2015 e Skype for Business Server 2019
  - Lync Server 2013 e Skype for Business Server 2019
  - Lync Server 2010, Lync Server 2013 e Skype for Business Server 2015 sono supportati, sia singolarmente che in ambienti con versioni miste.
- A partire dal 31 luglio 2022, per spostare gli utenti tra una distribuzione locale e il cloud, è necessario usare le versioni minime seguenti di Skype for Business Server o Lync Server:
</br>

|Prodotto locale|Versione minima richiesta|Compilazione minima richiesta|
|---|---|---|
|Skype for Business Server 2019| CU6 |7.0.2046.385|
|Skype for Business Server 2015| CU12|6.0.9319.619|
|Lync Server 2013| CU10 con hotfix 7|5.0.8308.1182|

</br>

> [!NOTE] 
> Lync Server 2010 non è supportato con Teams.


## <a name="multi-forest-support"></a>Supporto multiforesta

<a name="BKMK_MultiForest"> </a>

Microsoft supporta i tipi seguenti di scenari ibridi a più foreste:

- **Topologia della foresta di risorse** In questo tipo di topologia è presente una foresta che ospita Skype for Business Server (la foresta di risorse) e sono presenti una o più foreste aggiuntive che ospitano le identità dell'account, che accedono alla Skype for Business Server nella foresta di risorse. In generale, gli utenti possono accedere alla funzionalità Skype for Business in un'altra foresta se vengono soddisfatti i requisiti seguenti:
  - Gli utenti sono sincronizzati correttamente nella foresta che ospita Skype for Business. Nelle configurazioni ibride, ciò significa che gli utenti devono essere sincronizzati come oggetti utente disabilitati.
  - La foresta che ospita Skype for Business deve considerare attendibile la foresta contenente gli utenti.
    Per informazioni dettagliate sugli scenari ibridi della foresta di risorse, vedere [Distribuire una topologia di foresta di risorse per Skype for Business ibridi](configure-a-multi-forest-environment-for-hybrid.md).

- **Più distribuzioni di Skype for Business Server in più foreste.** Questa configurazione può verificarsi a seguito di scenari di fusione e acquisizione, nonché in aziende più complesse. È possibile consolidare tutti gli utenti dall'ambiente locale al cloud in una singola organizzazione di Microsoft 365 per qualsiasi organizzazione con più distribuzioni Skype for Business, a condizione che siano soddisfatti i requisiti chiave seguenti:
  - Deve essere presente al massimo un'organizzazione di Microsoft 365 coinvolta. Il consolidamento in scenari con più di un'organizzazione non è supportato.
  - In un determinato momento, solo una foresta di Skype for Business locale può essere in modalità ibrida (spazio di indirizzi SIP condiviso). Tutte le altre foreste Skype for Business locali devono rimanere completamente in locale (e presumibilmente federate tra loro). Si noti che queste altre organizzazioni locali possono eseguire la sincronizzazione con AAD se lo si desidera con [nuove funzionalità per disabilitare i domini SIP online disponibili a](/powershell/module/skype/disable-csonlinesipdomain) partire da dicembre 2018.

    I clienti con distribuzioni di Skype for Business in più foreste devono eseguire la migrazione completa di ogni foresta Skype for Business singolarmente nell'organizzazione di Microsoft 365 usando la funzionalità split-domain (Shared SIP Address Space). Al termine della migrazione della foresta, i clienti devono disabilitare l'ambiente ibrido con la distribuzione locale prima di procedere alla migrazione della distribuzione Skype for Business locale successiva. Inoltre, prima di essere migrati nel cloud, gli utenti locali rimangono in uno stato federato con tutti gli utenti non rappresentati nella directory locale dello stesso utente. Per altre informazioni, vedere [Consolidamento del cloud per Teams e Skype for Business](cloud-consolidation.md).

## <a name="federation-requirements"></a>Requisiti di federazione

<a name="BKMK_Federation"> </a>

Quando si configura Skype for Business modalità ibrida, è necessario assicurarsi che gli ambienti locali e online possano essere federati tra loro.  L'ambiente online ha una federazione aperta per impostazione predefinita; l'ambiente locale ha spesso una federazione chiusa per impostazione predefinita.  

Per configurare correttamente una distribuzione ibrida, è necessario soddisfare i requisiti seguenti:

- La corrispondenza del dominio deve essere configurata allo stesso modo per la distribuzione locale e l'organizzazione di Microsoft 365. Se l'individuazione dei partner è abilitata nella distribuzione locale, è necessario configurare la federazione aperta per l'organizzazione online. Se l'individuazione partner non è abilitata, la federazione chiusa deve essere configurata per l'organizzazione online.
- L'elenco Domini bloccati nella distribuzione locale deve corrispondere esattamente all'elenco Domini bloccati per il tenant online.
- L'elenco Domini consentiti nella distribuzione locale deve corrispondere esattamente all'elenco Domini consentiti per il tenant online.
- La federazione deve essere abilitata per le comunicazioni esterne per il tenant online.

## <a name="network-considerations"></a>Considerazioni sulla rete

Le sezioni seguenti descrivono le considerazioni per:

- Impostazioni DNS
- Considerazioni sul firewall

### <a name="dns-settings-for-hybrid-deployments"></a>Impostazioni DNS per le distribuzioni ibride

<a name="BKMK_DNS"> </a>

Quando si creano i record DNS per le distribuzioni ibride, tutti i record DNS esterni di Skype for Business devono puntare all'infrastruttura on-premise. Per informazioni dettagliate sui record DNS necessari, vedere [Requisiti DNS per Skype for Business Server](../../sfbserver/plan-your-deployment/network-requirements/dns.md).

Inoltre, è necessario assicurarsi che la risoluzione DNS descritta nella tabella seguente funzioni nella distribuzione on-premises. Se è già stata configurata la federazione per l'ambiente locale, è probabile che siano già presenti.

|Record DNS  <br/> |Risolvibile da  <br/> |Requisito DNS  <br/> |
|:-----|:-----|:-----|
|Record SRV DNS per _sipfederationtls._tcp.\<sipdomain.com\> per tutti i domini SIP supportati che si risolve in INDIRIZZI IP esterni di Access Edge  <br/> |Server Perimetrali  <br/> |Abilitare la comunicazione federata in una configurazione ibrida. Il server perimetrale deve sapere dove instradare il traffico federato per il dominio SIP diviso tra locale e online.  <br/> Deve usare la corrispondenza dei nomi DNS rigorosi tra il dominio nel nome utente e il record SRV.  <br/> |
|Record A DNS per l'FQDN del servizio Web Conferencing Edge, ad esempio webcon.contoso.com la risoluzione in IP esterni di Web Conferencing Edge  <br/> |Computer degli utenti collegati alla rete aziendale interna  <br/> |Consentite agli utenti online di presentare o visualizzare contenuti in riunioni ospitate in sede. I contenuti includono file PowerPoint, lavagne, sondaggi e note condivise.  <br/> |

A seconda di come è configurato il DNS nella vostra organizzazione, potrebbe essere necessario aggiungere questi record alla zona DNS interna ospitata per i domini SIP corrispondenti per fornire la risoluzione DNS interna a questi record.

### <a name="firewall-considerations-for-hybrid-deployments"></a>Considerazioni sul firewall per le distribuzioni ibride

<a name="BKMK_Firewall"> </a>

I computer della rete devono essere in grado di eseguire ricerche DNS standard su Internet. Se questi computer possono connettersi a siti Internet standard, la rete soddisfa questo requisito.

A seconda della posizione del data center di Microsoft Online Services, è anche necessario configurare i dispositivi del firewall di rete in modo che accettino connessioni in base ai nomi di dominio con caratteri jolly, ad esempio tutto il traffico da \*.outlook.com. Se i firewall dell'organizzazione non supportano configurazioni di nomi jolly, è necessario determinare manualmente gli intervalli di indirizzi IP che si desidera consentire e le porte specificate.

Per altre informazioni, inclusi i dettagli sulle porte e i requisiti del protocollo, vedere [URL e intervalli di indirizzi IP di Microsoft 365](/microsoft-365/enterprise/urls-and-ip-address-ranges).
