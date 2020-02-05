---
title: Pianificare la connessione ibrida | Integrazione di Office 365 in Skype for Business Server 2019
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Considerazioni sulla pianificazione per l'implementazione della connettività ibrida tra Skype for Business Server e Skype for business online o teams.
ms.openlocfilehash: 55986df708c1ce190605ecef77b3789ae7e55db5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756010"
---
# <a name="plan-hybrid-connectivity-between-skype-for-business-server-and-office-365"></a>Pianificare la connettività ibrida tra Skype for Business Server e Office 365

## <a name="overview"></a>Panoramica

Leggere questo argomento per informazioni su come pianificare la connettività ibrida tra Skype for Business Server e teams o Skype for business online. La configurazione della connettività ibrida è il primo passaggio per spostare l'ambiente locale nel cloud.

Se gli utenti di Skype for business in locale utilizzano anche team (affiancati), gli utenti non hanno la possibilità di interagire con gli utenti di Skype for business dal proprio client di teams, né di comunicare con gli utenti di organizzazioni federative, dalla propria Client teams. Per ottenere questa funzionalità nei team, questi utenti devono essere spostati da Skype for business in locale al cloud, che richiede la configurazione della modalità ibrida di Skype for business. Inoltre, per una migliore esperienza, questi utenti devono essere in modalità solo team, in modo da garantire tutte le chiamate in arrivo e le chat provenienti da qualsiasi utente che si trova nel client Teams dell'utente.

È inoltre necessario configurare la connettività ibrida e spostare tutti gli utenti nel cloud prima di rimuovere le autorizzazioni per la distribuzione di Skype for business locale.  Con la connettività ibrida configurata, è possibile scegliere di spostare gli utenti nel cloud in base alla pianificazione e alle esigenze aziendali. Con il routing diretto, è possibile sfruttare l'infrastruttura vocale locale quando si passa al cloud e al termine della migrazione.

In questo argomento vengono descritti i requisiti dell'infrastruttura e del sistema necessari per configurare la connettività ibrida tra la distribuzione di Skype for Business Server locale esistente e i team o Skype for business online.

Dopo aver letto questo argomento e aver pronto la configurazione della connettività ibrida, vedere [Configure Hybrid connectivity between Skype for Business Server and Office 365](configure-hybrid-connectivity.md). Negli argomenti di configurazione vengono fornite istruzioni dettagliate per configurare la connettività ibrida tra la distribuzione locale e i team o Skype for business online.

## <a name="about-shared-sip-address-space-functionality"></a>Informazioni sulla funzionalità dello spazio di indirizzi SIP condiviso

<a name="BKMK_Overview"> </a>

 Con la connettività ibrida configurata tra una distribuzione locale di Skype for Business Server e teams o Skype for business online, è possibile che alcuni utenti siano ospitati in locale e che alcuni utenti siano alloggiati online.

Questo tipo di configurazione si basa sulla funzionalità dello spazio di indirizzi SIP condiviso, a volte denominato "dominio diviso", ovvero gli utenti di un dominio, ad esempio contoso.com, vengono divisi tra l'utilizzo di Skype for Business Server in locale e in teams o Skype for business Online, come illustrato nel diagramma seguente:

![Connettività ibrida di questo-dominio diviso](../../sfbserver2019/media/plan-hybrid-connectivity-2019-1.png)

Quando viene configurato lo spazio degli indirizzi SIP condiviso:

- Azure Active Directory Connect viene utilizzato per sincronizzare la directory locale con Office 365.
- Gli utenti ospitati in locale interagiscono con i server Skype for business locali.
- Gli utenti ospitati online possono interagire con Skype for business online o con i servizi teams.
- Gli utenti di entrambi gli ambienti possono comunicare tra loro.
- Active Directory locale è autorevole. Tutti gli utenti devono essere creati prima in Active Directory locale e quindi sincronizzati con Azure AD. Anche se si desidera che l'utente sia ospitato online, è necessario innanzitutto creare l'utente nell'ambiente locale e quindi spostare l'utente in online per assicurarsi che l'utente sia individuabile dagli utenti locali.

Prima che un utente possa essere spostato online, all'utente deve essere assegnata una licenza di Skype for business online (piano 2). Se l'utente utilizzerà teams, all'utente deve anche essere assegnata una licenza per i team (e la licenza di Skype for business deve rimanere abilitata). Se gli utenti desiderano usufruire di altre funzionalità online, ad esempio audioconferenza o sistema telefonico, è necessario assegnare loro la licenza appropriata in Office 365.

## <a name="infrastructure-requirements"></a>Requisiti dell'infrastruttura

<a name="BKMK_Infrastructure"> </a>

Per implementare la connettività ibrida tra l'ambiente locale e i servizi di comunicazione di Office 365, è necessario soddisfare i requisiti di infrastruttura seguenti:

- Una singola distribuzione locale di Skype for Business Server o Lync Server distribuito in una topologia supportata. Vedere [requisiti della topologia](plan-hybrid-connectivity.md#BKMK_Topology) in questo argomento.
- Un tenant di Microsoft Office 365 con Skype for business online abilitato.
    > [!NOTE]
    > È possibile utilizzare solo un singolo tenant per una configurazione ibrida con la distribuzione locale.
- Azure Active Directory Connect per sincronizzare la directory locale con Office 365. Per ulteriori informazioni, vedere [Azure ad Connect: accounts and Permissions](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect-accounts-permissions).
- Strumenti di amministrazione di Skype for Business Server.  Questi sono necessari per spostare gli utenti da locale al cloud. Questi strumenti devono essere installati in un server con accesso sia alla distribuzione locale che a Internet.
- Strumenti di amministrazione online.  È possibile utilizzare l'interfaccia di amministrazione dei team o Windows PowerShell per gestire i team e Skype for business online. Per utilizzare PowerShell per gestire team o Skype for business online, scaricare e installare il connettore di Skype for business online.
- Lo spazio degli indirizzi SIP condiviso deve essere abilitato e la distribuzione locale deve essere configurata per l'utilizzo di Office 365 come provider di hosting. Per ulteriori informazioni sui passaggi necessari per configurare la connettività ibrida, vedere [Configure Hybrid Connectivity](configure-hybrid-connectivity.md).

Dopo aver configurato la connettività ibrida, è possibile spostare gli utenti in teams o in Skype for business online. Per ulteriori informazioni, vedere [spostare gli utenti da locale a teams](move-users-from-on-premises-to-teams.md) e [spostare gli utenti da locale a Skype for business online](move-users-from-on-premises-to-skype-for-business-online.md).

## <a name="server-version-requirements"></a>Requisiti per la versione server

<a name="BKMK_Topology"> </a>

Per configurare la distribuzione ibrida con **team o Skype for business online**, è necessario disporre di una delle topologie supportate seguenti:

- Una distribuzione di Skype for Business Server 2019 con tutti i server che eseguono Skype for Business Server 2019.
- Una distribuzione di Skype for Business Server 2015 con tutti i server che eseguono Skype for Business Server 2015.
- Una distribuzione di Lync Server 2013 con tutti i server che eseguono Lync Server 2013.  Tuttavia, se è necessaria la connettività vocale ibrida, è necessario utilizzare una topologia a versione mista, come indicato di seguito.
- Una distribuzione con un massimo di 2 versioni server diverse, come elencato di seguito:
  - Skype for Business Server 2015 e Skype for Business Server 2019
  - Lync Server 2013 e Skype for Business Server 2019
  - Lync Server 2013 e Skype for Business Server 2015

*Se si desidera che la voce ibrida sia consentita in qualsiasi topologia*, sia il server perimetrale definito come Edge federativo che il pool associato alla federazione SIP devono eseguire Skype for business 2015 o versione successiva. Se disponibile, gli utenti possono rimanere in un pool Lync 2013. Per ulteriori informazioni, vedere [pianificare il sistema telefonico con connettività PSTN in Skype for Business Server](https://docs.microsoft.com/en-us/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity).

Le topologie seguenti che includono **Lync Server 2010 sono supportate con Skype for business online** per la messaggistica istantanea e le riunioni.  Le topologie che includono **Lync Server 2010 non sono supportate per la voce ibrida o i team**.

- Distribuzione mista di Lync Server 2010 e Skype for Business Server 2015
- Distribuzione di Lync Server 2010 e Lync Server 2013 mista
- Una distribuzione di Lync Server 2010 con tutti i server che eseguono Lync Server 2010 con gli aggiornamenti cumulativi più recenti.

È necessario che il server perimetrale federativo e il server dell'hop successivo del server perimetrale federativo esegua l'esecuzione di Lync Server 2010 con gli aggiornamenti cumulativi più recenti. Gli strumenti di amministrazione di Skype for Business Server 2015 o Lync Server 2013 devono essere installati in almeno un server o una workstation di gestione.

## <a name="multi-forest-support"></a>Supporto per più foreste

<a name="BKMK_MultiForest"> </a>

Microsoft supporta i seguenti tipi di scenari ibridi a più foreste:

- **Topologia della foresta di risorse.** In questo tipo di topologia, è presente una foresta che ospita Skype for Business Server (la foresta di risorse) e vi sono una o più foreste aggiuntive che ospitano le identità degli account, che accedono al server Skype for business nella foresta di risorse. In generale, gli utenti possono accedere alle funzionalità di Skype for business in un altro insieme di strutture se vengono soddisfatti i requisiti seguenti:
  - Gli utenti sono adeguatamente sincronizzati nella foresta che ospita Skype for business. Nelle configurazioni ibride, questo significa che gli utenti devono essere sincronizzati come oggetti utente disabilitati.
  - La foresta che ospita Skype for business deve considerare attendibile la foresta contenente gli utenti.
    Per informazioni dettagliate sugli scenari ibridi della foresta di risorse, vedere [deploy a Resource Forest topologie for Hybrid Skype for business](configure-a-multi-forest-environment-for-hybrid.md).
- **Più distribuzioni di Skype for Business Server in più foreste.** Questa configurazione può verificarsi a causa degli scenari di fusione e acquisizione, nonché in imprese più complesse.  Il consolidamento di tutti gli utenti da locale al cloud in un unico tenant di Office 365 può essere raggiunto per qualsiasi organizzazione con più distribuzioni di Skype for business, purché vengano soddisfatti i requisiti chiave seguenti:

  - La maggior parte dei tenant di Office 365 è coinvolta. Il consolidamento in scenari con più di un tenant di Office 365 non è supportato.
  - In un determinato momento, solo una foresta Skype for business locale può essere in modalità ibrida (spazio di indirizzi SIP condiviso). Tutte le altre foreste di Skype for business locali devono rimanere completamente in locale (e presumibilmente federata tra loro). Si noti che queste altre organizzazioni locali possono sincronizzarsi con AAD, se lo si desidera, con [nuove funzionalità per disabilitare i domini SIP online](https://docs.microsoft.com/en-us/powershell/module/skype/disable-csonlinesipdomain) disponibili al 2018 dicembre.

    I clienti con distribuzioni di Skype for business in più foreste devono migrare completamente ogni foresta di Skype for business singolarmente nel tenant di Office 365 utilizzando la funzionalità di Split-Domain (spazio di indirizzi SIP condiviso) e quindi disabilitare l'ibrido con l' distribuzione locale, prima di procedere alla migrazione della successiva distribuzione di Skype for business locale. Inoltre, prima di essere migrati nel cloud, gli utenti locali restano in uno stato federato con tutti gli utenti che non sono rappresentati nella stessa directory locale dell'utente. Per ulteriori informazioni, vedere [cloud Consolidation for teams e Skype for business](cloud-consolidation.md).

## <a name="federation-requirements"></a>Requisiti di Federazione

<a name="BKMK_Federation"> </a>

Durante la configurazione di un ambiente ibrido, è necessario assicurarsi che gli ambienti locali e online possano essere federati tra loro.  Per impostazione predefinita, l'ambiente online dispone di una federazione aperta. l'ambiente locale ha spesso una federazione chiusa per impostazione predefinita.  

Per configurare correttamente una distribuzione ibrida, è necessario soddisfare i requisiti seguenti:

- La corrispondenza del dominio deve essere configurata per la distribuzione locale e per il tenant di Office 365. Se l'individuazione dei partner è abilitata nella distribuzione locale, è necessario configurare la Federazione aperta per il tenant online. Se l'individuazione dei partner non è abilitata, la federazione chiusa deve essere configurata per il tenant online.
- L'elenco dei domini bloccati nella distribuzione locale deve corrispondere esattamente all'elenco dei domini bloccati per il tenant online.
- L'elenco dei domini consentiti nella distribuzione locale deve corrispondere esattamente all'elenco dei domini consentiti per il tenant online.
- La Federazione deve essere abilitata per le comunicazioni esterne per il tenant online.

## <a name="network-considerations"></a>Considerazioni sulla rete

Nelle sezioni seguenti vengono descritte le considerazioni relative a:

- Impostazioni DNS
- Considerazioni sul firewall

### <a name="dns-settings"></a>Impostazioni DNS

<a name="BKMK_DNS"> </a>

Quando si creano record DNS per le distribuzioni ibride, tutti i record DNS esterni di Skype for business devono puntare all'infrastruttura locale. Per informazioni dettagliate sui record DNS necessari, fare riferimento ai [requisiti DNS per Skype for Business Server](../../sfbserver/plan-your-deployment/network-requirements/dns.md).

Inoltre, è necessario assicurarsi che la risoluzione DNS descritta nella tabella seguente sia compatibile con la distribuzione locale. Se è già stata configurata la Federazione per l'ambiente locale, è probabile che siano già presenti.

|Record DNS  <br/> |Risolvibile da  <br/> |Requisito DNS  <br/> |
|:-----|:-----|:-----|
|Record SRV DNS per _sipfederationtls. _tcp. \<SipDomain.com\> per tutti i domini SIP supportati che si risolvono in Access Edge IP esterni (s)  <br/> |Server perimetrali  <br/> |Abilitare la comunicazione federata in una configurazione ibrida. Il server perimetrale deve sapere dove instradare il traffico federato per il dominio SIP suddiviso tra locali e online.  <br/> Deve utilizzare la corrispondenza del nome DNS rigorosa tra il dominio nel nome utente e il record SRV.  <br/> |
|DNS un record (s) per FQDN del servizio Web Conferencing Edge, ad esempio webcon.contoso.com che si risolvono in Web Conferencing Edge IP esterno (s)  <br/> |Computer degli utenti connessi alla rete aziendale interna  <br/> |Consente agli utenti online di presentare o visualizzare il contenuto nelle riunioni ospitate locali. Il contenuto include file di PowerPoint, lavagne, sondaggi e note condivise.  <br/> |

A seconda del modo in cui il DNS è configurato nell'organizzazione, potrebbe essere necessario aggiungere questi record all'area DNS interna ospitata per i domini SIP corrispondenti per fornire la risoluzione DNS interna a questi record.

### <a name="firewall-considerations"></a>Considerazioni sul firewall

<a name="BKMK_Firewall"> </a>

I computer della rete devono essere in grado di eseguire ricerche DNS standard su Internet. Se questi computer possono connettersi a siti Internet standard, la rete soddisfa questo requisito.

A seconda della posizione del data center dei Microsoft Online Services, è inoltre necessario configurare i dispositivi firewall di rete in modo che accettino connessioni basate su nomi di dominio con caratteri jolly, \*ad esempio tutto il traffico proveniente da. Outlook.com. Se i firewall dell'organizzazione non supportano le configurazioni del nome con caratteri jolly, sarà necessario determinare manualmente gli intervalli di indirizzi IP che si desidera consentire e le porte specificate.

Per ulteriori informazioni, inclusi i dettagli sulle porte e i requisiti di protocollo, vedere [URL e intervalli di indirizzi IP di Office 365](https://go.microsoft.com/fwlink/p/?LinkId=252942).
