---
title: Pianificare la connessione ibrida | Integrazione di Office 365 in Skype for Business Server 2019
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
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
description: Considerazioni sulla pianificazione per l'implementazione della connettività ibrida tra Skype for Business Server e Skype for business online o teams.
ms.openlocfilehash: 2cca98740aeb991923683ce80b3b33a6ac49fbc6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36185435"
---
# <a name="plan-hybrid-connectivity-between-skype-for-business-server-and-office-365"></a>Pianificare la connettività ibrida tra Skype for Business Server e Office 365

## <a name="overview"></a>Panoramica

Leggere questo argomento per informazioni su come pianificare la connettività ibrida tra Skype for Business Server e teams o Skype for business online. La configurazione della connettività ibrida è il primo passaggio per spostare l'ambiente locale nel cloud.

Gli utenti di Skype for business locali che usano Team (affiancati) non hanno la possibilità di interagire con gli utenti di Skype for business dal proprio client di teams, né comunicare con gli utenti di organizzazioni federate, dalle loro Client teams. Per ottenere questa funzionalità in teams, questi utenti devono essere spostati da Skype for business locale al cloud, che richiede la configurazione della modalità ibrida di Skype for business. Inoltre, per una migliore esperienza, questi utenti devono essere in modalità solo teams, che garantisce tutte le chiamate in arrivo e le chat da qualsiasi utente nel client Teams dell'utente.

È anche necessario configurare la connettività ibrida e spostare tutti gli utenti nel cloud prima di eseguire la disattivazione della distribuzione di Skype for business locale.  Con la configurazione della connettività ibrida, è possibile scegliere di trasferire gli utenti nel cloud in base alla pianificazione e alle esigenze aziendali. Con il routing diretto, è possibile sfruttare l'infrastruttura vocale locale mentre si passa al cloud e dopo il completamento della migrazione.

Questo argomento descrive i requisiti di infrastruttura e di sistema necessari per configurare la connettività ibrida tra la distribuzione e i team di Skype for Business Server esistenti o Skype for business online.

Dopo aver letto questo argomento e essere pronti per configurare la connettività ibrida, vedere [configurare la connettività ibrida tra Skype for Business Server e Office 365](configure-hybrid-connectivity.md). Gli argomenti della configurazione includono indicazioni dettagliate per configurare la connettività ibrida tra la distribuzione locale e i team o Skype for business online.

## <a name="about-shared-sip-address-space-functionality"></a>Informazioni sulla funzionalità spazio di indirizzi SIP condiviso

<a name="BKMK_Overview"> </a>

 Con la connettività ibrida configurata tra una distribuzione locale di Skype for Business Server e teams o Skype for business online, è possibile avere alcuni utenti ospitati in locale e alcuni utenti online.

Questo tipo di configurazione si basa sulla funzionalità di spazio di indirizzi SIP condiviso e viene talvolta definito "dominio diviso", ovvero gli utenti di un dominio, ad esempio contoso.com, vengono divisi tra l'uso di Skype for Business Server in locale e in teams o in Skype for business Online, come illustrato nel diagramma seguente:

![Connettività ibrida di SfB-dominio diviso](../../sfbserver2019/media/plan-hybrid-connectivity-2019-1.png)

Quando è configurato lo spazio di indirizzi SIP condiviso:

- Azure Active Directory Connect viene usato per sincronizzare la directory locale con Office 365.
- Gli utenti ospitati in locale interagiscono con i server Skype for business locale.
- Gli utenti ospitati online possono interagire con Skype for business online o con i servizi teams.
- Gli utenti di entrambi gli ambienti possono comunicare tra loro.
- Active Directory locale è autorevole. Tutti gli utenti devono essere creati prima in Active Directory locale e quindi sincronizzati con Azure AD. Anche se si prevede che l'utente sia ospitato online, è necessario prima di tutto creare l'utente nell'ambiente locale e quindi spostarlo in online per verificare che l'utente sia individuabile dagli utenti locali.

Prima che un utente possa essere spostato online, all'utente deve essere assegnata una licenza di Skype for business online (piano 2). Se l'utente utilizzerà teams, all'utente deve essere assegnata anche una licenza di Teams (e la licenza Skype for business deve rimanere abilitata). Se gli utenti desiderano sfruttare le caratteristiche online aggiuntive, ad esempio i servizi di audioconferenza o il sistema telefonico, è necessario assegnare loro la licenza appropriata in Office 365.

## <a name="infrastructure-requirements"></a>Requisiti per l'infrastruttura

<a name="BKMK_Infrastructure"> </a>

Per implementare la connettività ibrida tra l'ambiente locale e i servizi di comunicazione di Office 365, è necessario soddisfare i requisiti di infrastruttura seguenti:

- Una singola distribuzione locale di Skype for Business Server o Lync Server distribuito in una topologia supportata. Vedere [requisiti](plan-hybrid-connectivity.md#BKMK_Topology) della topologia in questo argomento.
- Un tenant di Microsoft Office 365 con Skype for business online abilitato.
    > [!NOTE]
    > È possibile usare solo un singolo tenant per una configurazione ibrida con la distribuzione locale.
- Azure Active Directory si connette per sincronizzare la directory locale con Office 365. Per altre informazioni, vedere [Azure ad Connect: account e autorizzazioni](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect-accounts-permissions).
- Strumenti di amministrazione di Skype for Business Server.  Questi sono necessari per trasferire gli utenti dal locale al cloud. Questi strumenti devono essere installati in un server con accesso sia alla distribuzione locale che a Internet.
- Strumenti di amministrazione online.  Puoi usare l'interfaccia di amministrazione di teams o Windows PowerShell per gestire teams e Skype for business online. Per usare PowerShell per gestire team o Skype for business online, scaricare e installare il connettore Skype for business online.
- Lo spazio di indirizzi SIP condiviso deve essere abilitato e la distribuzione locale deve essere configurata in modo da usare Office 365 come provider di hosting. Per altre informazioni sui passaggi necessari per configurare la connettività ibrida, vedere [configurare la connettività ibrida](configure-hybrid-connectivity.md).

Dopo aver configurato la connettività ibrida, è possibile trasferire gli utenti in teams o in Skype for business online. Per altre informazioni, vedere [trasferire utenti da locale a teams](move-users-from-on-premises-to-teams.md) e [trasferire utenti da locali a Skype for business online](move-users-from-on-premises-to-skype-for-business-online.md).

## <a name="server-version-requirements"></a>Requisiti della versione del server

<a name="BKMK_Topology"> </a>

Per configurare la distribuzione ibrida con **Teams o Skype for business online**, è necessario disporre di una delle topologie supportate seguenti:

- Una distribuzione di Skype for Business Server 2019 con tutti i server che utilizzano Skype for Business Server 2019.
- Una distribuzione di Skype for Business Server 2015 con tutti i server che utilizzano Skype for Business Server 2015.
- Una distribuzione di Lync Server 2013 con tutti i server che utilizzano Lync Server 2013.  Tuttavia, se è necessaria la connettività vocale ibrida, è necessario usare una topologia a versione mista, come indicato di seguito.
- Una distribuzione con un massimo di 2 versioni diverse del server elencate di seguito:
  - Skype for Business Server 2015 e Skype for Business Server 2019
  - Lync Server 2013 e Skype for Business Server 2019
  - Lync Server 2013 e Skype for Business Server 2015

*Se si desidera una voce ibrida in qualsiasi topologia*, sia l'Edge Server designato come bordo federativo che il pool associato alla federazione SIP devono eseguire Skype for business 2015 o versione successiva. Se disponibile, gli utenti possono rimanere in un pool di Lync 2013. Per altre informazioni, Vedi [pianificare il sistema telefonico con connettività PSTN in Skype for Business Server](https://docs.microsoft.com/en-us/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity).

Le topologie seguenti che includono **Lync Server 2010 sono supportate con Skype for business online** per la messaggistica istantanea e le riunioni.  Le topologie che includono **Lync Server 2010 non sono supportate per la voce ibrida né per i team**.

- Distribuzione di Lync Server 2010 e Skype for Business Server 2015 mista
- Distribuzione di Lync Server 2010 e Lync Server 2013 mista
- Una distribuzione di Lync Server 2010 con tutti i server che utilizzano Lync Server 2010 con gli aggiornamenti cumulativi più recenti.

La Federazione Edge Server e il server hop successivo del server Edge federativo devono eseguire Lync Server 2010 con gli aggiornamenti cumulativi più recenti. Gli strumenti di amministrazione di Skype for Business Server 2015 o Lync Server 2013 devono essere installati in almeno un server o una workstation di gestione.

## <a name="multi-forest-support"></a>Supporto per più insiemi di strutture

<a name="BKMK_MultiForest"> </a>

Microsoft supporta i tipi di scenari ibridi multiforesta seguenti:

- **Topologia della foresta di risorse.** In questo tipo di topologia esiste una foresta che ospita Skype for Business Server (la foresta delle risorse) e sono presenti una o più foreste aggiuntive che ospitano le identità degli account, che accedono a Skype for Business Server nella foresta di risorse. In generale, gli utenti possono accedere alle funzionalità di Skype for business in un'altra foresta se sono soddisfatti i requisiti seguenti:
  - Gli utenti vengono sincronizzati correttamente nella foresta che ospita Skype for business. Nelle configurazioni ibride questo significa che gli utenti devono essere sincronizzati come oggetti utente disabilitati.
  - La foresta che ospita Skype for business deve considerare attendibile la foresta che contiene gli utenti.
    Per informazioni dettagliate sugli scenari ibridi della foresta di risorse, vedere [distribuire una topologia di foresta di risorse per Skype for business ibrido](configure-a-multi-forest-environment-for-hybrid.md).
- **Più distribuzioni di Skype for Business Server in più foreste.** Questa configurazione può presentarsi come risultato degli scenari di fusione e acquisizione, nonché in imprese più complesse.  Il consolidamento di tutti gli utenti dal locale al cloud in un unico tenant di Office 365 può essere realizzato per qualsiasi organizzazione con più distribuzioni di Skype for business, a condizione che siano soddisfatti i requisiti chiave seguenti:

  - È necessario che al massimo un tenant di Office 365 sia coinvolto. Il consolidamento in scenari con più di un tenant di Office 365 non è supportato.
  - In qualsiasi momento, una sola foresta Skype for business locale può essere in modalità ibrida (spazio di indirizzi SIP condiviso). Tutte le altre foreste di Skype for business locali devono rimanere completamente in locale (e presumibilmente federate tra loro). Tieni presente che queste altre organizzazioni locali possono eseguire la sincronizzazione con AAD, se necessario, con [nuove funzionalità per disabilitare i domini SIP online](https://docs.microsoft.com/en-us/powershell/module/skype/disable-csonlinesipdomain) disponibili a partire da dicembre 2018.

    I clienti con distribuzioni di Skype for business in più foreste devono eseguire la migrazione completa di ogni foresta di Skype for business singolarmente nel tenant di Office 365 usando la funzionalità Split-Domain (spazio di indirizzi SIP condiviso) e quindi disabilitare Hybrid con il distribuzione locale, prima di passare alla migrazione della nuova distribuzione locale di Skype for business. Inoltre, prima di essere migrati nel cloud, gli utenti locali restano in uno stato federato con tutti gli utenti che non sono rappresentati nella stessa directory locale dell'utente. Per altre informazioni, Vedi [consolidamento del cloud per Teams e Skype for business](cloud-consolidation.md).

## <a name="federation-requirements"></a>Requisiti federativi

<a name="BKMK_Federation"> </a>

Quando configuri Hybrid, devi assicurarti che gli ambienti locali e online possano essere federati tra loro.  Per impostazione predefinita, l'ambiente online è Open Federation; l'ambiente locale ha spesso una federazione chiusa per impostazione predefinita.  

Per configurare correttamente una distribuzione ibrida, è necessario soddisfare i requisiti seguenti:

- La corrispondenza dei domini deve essere configurata per la distribuzione locale e per il tenant di Office 365. Se l'individuazione dei partner è abilitata nella distribuzione locale, la Federazione aperta deve essere configurata per il tenant online. Se l'individuazione dei partner non è abilitata, la federazione chiusa deve essere configurata per il tenant online.
- L'elenco dei domini bloccati nella distribuzione locale deve corrispondere esattamente all'elenco dei domini bloccati per il tenant online.
- L'elenco dei domini consentiti nella distribuzione locale deve corrispondere esattamente all'elenco dei domini consentiti per il tenant online.
- La Federazione deve essere abilitata per le comunicazioni esterne per il tenant online.

## <a name="network-considerations"></a>Considerazioni sulla rete

Le sezioni seguenti descrivono le considerazioni relative a:

- Impostazioni DNS
- Considerazioni sul firewall

### <a name="dns-settings"></a>Impostazioni DNS

<a name="BKMK_DNS"> </a>

Quando crei record DNS per distribuzioni ibride, tutti i record DNS esterni di Skype for business dovrebbero puntare all'infrastruttura locale. Per informazioni dettagliate sui record DNS necessari, vedere [requisiti DNS per Skype for Business Server](../../sfbserver/plan-your-deployment/network-requirements/dns.md).

Inoltre, è necessario assicurarsi che la risoluzione DNS descritta nella tabella seguente funzioni nella distribuzione locale. Se è già stata configurata la Federazione per locali, è probabile che siano già presenti.

|Record DNS  <br/> |Risolvibile da  <br/> |Requisito DNS  <br/> |
|:-----|:-----|:-----|
|Record SRV DNS per _sipfederationtls. _tcp. \<SipDomain.com\> per tutti i domini SIP supportati per la risoluzione di Access Edge IP esterni (s)  <br/> |Server perimetrale (s)  <br/> |Abilitare la comunicazione federata in una configurazione ibrida. Il server perimetrale deve sapere dove instradare il traffico federativo per il dominio SIP diviso tra locale e online.  <br/> Deve usare la corrispondenza di nomi DNS strict tra il dominio nel nome utente e il record SRV.  <br/> |
|DNS un record per il nome di dominio completo del servizio di conferenza Web Edge, ad esempio webcon.contoso.com che risolve in Web Conferencing Edge IP esterni (s)  <br/> |Computer degli utenti connessi alla rete aziendale interna  <br/> |Consentire agli utenti online di presentare o visualizzare contenuti in riunioni ospitate in locale. Il contenuto include file di PowerPoint, lavagne, sondaggi e note condivise.  <br/> |

A seconda del modo in cui il DNS è configurato nell'organizzazione, potrebbe essere necessario aggiungere questi record all'area DNS ospitata interna per i rispettivi domini SIP per ottenere la risoluzione DNS interna di questi record.

### <a name="firewall-considerations"></a>Considerazioni sul firewall

<a name="BKMK_Firewall"> </a>

I computer della rete devono essere in grado di eseguire ricerche DNS Internet standard. Se questi computer possono raggiungere siti Internet standard, la rete soddisfa questo requisito.

A seconda della posizione del centro dati di Microsoft Online Services, è necessario configurare anche i dispositivi firewall di rete per accettare connessioni basate sui nomi di dominio con caratteri jolly, ad esempio tutto \*il traffico da. Outlook.com. Se i firewall dell'organizzazione non supportano le configurazioni con nome jolly, sarà necessario determinare manualmente gli intervalli di indirizzi IP che si desidera consentire e le porte specificate.

Per altre informazioni, inclusi i dettagli sulle porte e i requisiti di protocollo, vedere [URL e intervalli di indirizzi IP di Office 365](https://go.microsoft.com/fwlink/p/?LinkId=252942).
