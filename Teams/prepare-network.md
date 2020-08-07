---
title: Preparare la rete dell'organizzazione per Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: jastark, kojika
audience: admin
description: Informazioni sulla preparazione della rete dell'organizzazione per Microsoft teams, inclusi i requisiti di rete, l'ottimizzazione della rete e i requisiti di larghezza di banda.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom:
- seo-marvel-mar2020
ms.openlocfilehash: d0ce589ef972639928e4c8696f3ed23146126086
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583891"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a>Preparare la rete dell'organizzazione per Microsoft Teams 

## <a name="network-requirements"></a>Requisiti di rete

Se è già stata [ottimizzata la rete per microsoft 365 o Office 365](https://docs.microsoft.com/Office365/Enterprise/assessing-network-connectivity), è probabile che sia pronta per Microsoft teams. In ogni caso-e soprattutto se si distribuisce rapidamente team come primo carico di lavoro di Microsoft 365 o Office 365 per supportare i **dipendenti remoti** : verificare quanto segue prima di iniziare l'implementazione del team.

1.  Tutte le posizioni hanno accesso a Internet (in modo che possano connettersi a Microsoft 365 o Office 365)? Come minimo, oltre al normale traffico Web, verificare di avere aperto gli elementi seguenti per tutte le posizioni, per i supporti in teams:

    |  |  |
    |---------|---------|
    |Porte     |Porte UDP da <strong>3478</strong> a <strong>3481</strong>        |
    |[Indirizzi IP](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) |<strong>13.107.64.0/18</strong>, <strong>52.112.0.0/14</strong>e <strong>52.120.0.0/14</strong>         |

> [!IMPORTANT]
> Se è necessario eseguire la Federazione con Skype for business, sia in locale che online, è necessario configurare alcuni record DNS aggiuntivi.
>
>|Record CNAME/nome host  |TTL  |Punta all'indirizzo o al valore  |
>|---------|---------|---------|
>|SIP     |    3600     |    sipdir.online.lync.com     |
>|Lyncdiscover     |   3600      |    webdir.online.lync.com     |
>


    
2.  Si dispone di un dominio verificato per Microsoft 365 o Office 365 (ad esempio, contoso.com)?
    
      - Se l'organizzazione non ha implementato Microsoft 365 o Office 365, vedere [Introduzione](https://docs.microsoft.com/microsoft-365/admin/admin-overview/get-started-with-office-365).
      - Se l'organizzazione non ha aggiunto o configurato un dominio verificato per Microsoft 365 o Office 365, vedere le [domande frequenti sui domini](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq).

3.  L'organizzazione ha distribuito Exchange Online e SharePoint Online?
    
      - Se l'organizzazione non ha Exchange Online, vedere [informazioni su come interagire con Exchange e Microsoft teams](exchange-teams-interact.md).
      - Se l'organizzazione non ha SharePoint Online, vedere [informazioni sul modo in cui SharePoint Online e OneDrive for business interagiscono con Microsoft teams](sharepoint-onedrive-interact.md).

Dopo aver verificato che si soddisfano questi requisiti di rete, è possibile che si sia pronti a [implementare team](How-to-roll-out-teams.md). Se si è una grande azienda multinazionale o si è certi di avere alcune limitazioni di rete, leggere per scoprire come valutare e ottimizzare la rete per i team.

> [!IMPORTANT]
> **Per gli istituti di istruzione**: se l'organizzazione è un Istituto di istruzione e si usa un sistema di informazioni per studenti (SIS), [distribuire School Data Sync](https://docs.microsoft.com/schooldatasync/) prima di implementare teams.
>  
> **In uso in locale Skype for Business Server**: se l'organizzazione è in uso in locale Skype for Business Server (o Lync Server), è necessario [configurare Azure ad Connect](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-azure-ad-connect) per sincronizzare la directory locale con Microsoft 365 o Office 365.

### <a name="best-practice-monitor-your-network-using-cqd-and-call-analytics"></a>Procedure consigliate: monitorare la rete usando Call Quality dashboard e le analisi delle chiamate 

Usare il [dashboard qualità chiamata (Call Quality Dashboard)](turning-on-and-using-call-quality-dashboard.md) per ottenere informazioni sulla qualità delle chiamate e delle riunioni in teams. Call Quality dashboard può aiutarti a ottimizzare la rete, tenendo d'occhio la qualità, l'affidabilità e l'esperienza utente. Call Quality dashboard analizza la telemetria aggregata per un'intera organizzazione in cui i modelli generali possono diventare evidenti, che consente di identificare i problemi e pianificare il risanamento. Inoltre, Call Quality dashboard offre report di metriche avanzate che offrono informazioni generali sulla qualità, l'affidabilità e l'esperienza utente. 

Userai [analisi delle chiamate](set-up-call-analytics.md) per analizzare i problemi di chiamata e riunione per un singolo utente.

## <a name="network-optimization"></a>Ottimizzazione della rete

Le attività seguenti sono facoltative e non sono necessarie per l'implementazione di Team, specialmente se si è una piccola azienda e si è già implementato Microsoft 365 o Office 365. Usare queste linee guida per ottimizzare le prestazioni di rete e teams oppure, se si è certi di avere alcune limitazioni di rete.

È consigliabile eseguire un'ulteriore ottimizzazione della rete se:

  - Le squadre si avviano lentamente (forse la larghezza di banda non è sufficiente)
  - Chiamate Keep dropping (potrebbe essere dovuto a firewall o bloccanti proxy)
  - Le chiamate sono statiche e ritagliate o le voci sembrano robot (potrebbe essere jitter o perdita di pacchetti)

Per una discussione approfondita sull'ottimizzazione della rete, tra cui indicazioni per identificare e risolvere i problemi di rete, leggere i principi di connettività di rete di [Microsoft 365 e Office 365](https://aka.ms/pnc).

<table>
<thead>
<tr class="header">
<th><strong>Attività di ottimizzazione della rete</strong></th>
<th><strong>Dettagli</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Pianificazione di rete</td>
<td><p>Per informazioni sulla valutazione della rete, inclusi i calcoli della larghezza di banda e i requisiti di rete nei percorsi fisici dell'organizzazione, vedere lo strumento <a href="https://docs.microsoft.com/microsoftteams/network-planner">Network Planner</a> nell'interfaccia di <a href="https://admin.teams.microsoft.com">amministrazione di teams</a>. Quando fornisci i dettagli della rete e l'uso dei team, Network Planner calcola i requisiti di rete per la distribuzione di team e la voce cloud tra le posizioni fisiche dell'organizzazione.</p>
<p>Per un esempio di scenario, vedere <a href="https://docs.microsoft.com/microsoftteams/tutorial-network-planner-example">utilizzo di Network Planner-esempio di scenario</a>.</p></td>
</tr>
<tr class="even">
<td>Advisor per Teams</td>
<td><a href="https://docs.microsoft.com/microsoftteams/use-advisor-teams-roll-out">Advisor per Teams</a> fa parte dell'interfaccia di <a href="https://admin.teams.microsoft.com">amministrazione di teams</a>. Valuta l'ambiente di Microsoft 365 o Office 365 e identifica le configurazioni più comuni che può essere necessario aggiornare o modificare prima che sia possibile implementare correttamente Teams.</td>
</tr>
<tr class="odd">
<td>Risoluzione dei nomi esterni</td>
<td>Assicurarsi che tutti i computer che eseguono il client teams possano risolvere le query DNS esterne per individuare i servizi forniti da Microsoft 365 o Office 365 e che i firewall non impediscano l'accesso. Per informazioni sulla configurazione delle porte del firewall, vedere <a href="https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges">URL e intervalli di indirizzi IP di Microsoft 365 e Office 365</a>.</td>
</tr>
<tr class="odd">
<td>Gestire la persistenza della sessione</td>
<td>Verificare che il firewall non modifichi gli indirizzi NAT (Network Address Translation) o le porte per UDP.</td>
</tr><tr class="odd">
<td>Convalidare le dimensioni del pool NAT</td>
<td>Convalidare le dimensioni del pool NAT (Network Address Translation) necessarie per la connettività degli utenti. Quando più utenti e dispositivi accedono a Microsoft 365 o Office 365 tramite <a href="https://docs.microsoft.com/office365/enterprise/nat-support-with-office-365">NAT (Network Address Translation) o Pat (Port Address Translation)</a>, è necessario assicurarsi che i dispositivi nascosti dietro ogni indirizzo IP instradabile pubblicamente non superino il numero supportato. Verificare che gli indirizzi IP pubblici adeguati vengano assegnati ai pool NAT per evitare l'esaurimento della porta. L'esaurimento della porta contribuirà agli utenti e ai dispositivi interni non essendo in grado di connettersi al servizio Microsoft 365 o Office 365.</td>
</tr>
<tr class="even">
<td>Routing a Microsoft Data Center</td>
<td><a href="https://docs.microsoft.com/office365/enterprise/client-connectivity">Implementare il routing più efficiente per i Data Center Microsoft</a>. Identificare le posizioni che possono usare i punti di uscita locali o regionali per connettersi alla rete Microsoft nel modo più efficiente possibile.</td>
</tr>
<tr class="odd">
<td>Istruzioni per il rilevamento delle intrusioni e la prevenzione</td>
<td>Se l'ambiente ha un sistema di <a href="https://docs.microsoft.com/azure/network-watcher/network-watcher-intrusion-detection-open-source-tools">rilevamento delle intrusioni</a> o di prevenzione (IDS/IPS) distribuito per un ulteriore livello di sicurezza per le connessioni in uscita, assicurarsi di consentire tutti gli URL di Microsoft 365 o Office 365.</td>
</tr>
<tr class="even">
<td>Configurare la VPN a tunnel separato</td>
<td><p>Ti consigliamo di specificare un percorso alternativo per il traffico di team che bypassa la rete privata virtuale (VPN), comunemente nota come [VPN a tunnel separato](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-routing). Split tunneling indica che il traffico per Microsoft 365 o Office 365 non passa attraverso la rete VPN, ma passa invece direttamente a Microsoft 365 o Office 365. L'esclusione della VPN avrà un impatto positivo sulla qualità dei team e riduce il carico dei dispositivi VPN e della rete dell'organizzazione. Per implementare una VPN con tunnel separato, usare il proprio fornitore di VPN.</p>
<p>Altri motivi per cui è consigliabile ignorare la VPN:
<ul>
<li><p>Le VPN in genere non sono progettate o configurate per supportare elementi multimediali in tempo reale.</p></li> 
<li><p>Alcune VPN potrebbero anche non supportare UDP (richiesto per i team).</p></li> 
<li><p>Le VPN introducono anche un ulteriore livello di crittografia sulla parte superiore del traffico multimediale già crittografato.</p></li> 
<li><p>La connettività a teams potrebbe non essere efficiente a causa del traffico di pinning dei capelli attraverso un dispositivo VPN.</p></li></td>
</tr>
<tr class="odd">
<td>Implementare QoS</td>
<td><a href="https://docs.microsoft.com/microsoftteams/qos-in-teams">Usare la qualità del servizio (QoS)</a> per configurare la priorità dei pacchetti. Questo migliorerà la qualità delle chiamate in teams e ti aiuterà a monitorare e risolvere i problemi di qualità delle chiamate. La QoS deve essere implementata in tutti i segmenti di una rete gestita. Anche quando una rete è stata adeguatamente provisionata per la larghezza di banda, QoS offre soluzioni di prevenzione dei rischi in caso di eventi di rete non previsti. Con QoS, il traffico vocale è prioritario in modo che questi eventi imprevisti non incidano negativamente sulla qualità.</td>
</tr>
<tr class="even">
<td>Ottimizzare il WiFi</td>
<td><p>Analogamente a VPN, le reti WiFi non sono necessariamente progettate o configurate per supportare elementi multimediali in tempo reale. La pianificazione o l'ottimizzazione di una rete WiFi per il supporto dei team è una considerazione importante per una distribuzione di alta qualità. Considerare questi fattori:</p>
<ul>
<li><p>Implementare QoS o WiFi Multimedia (WMM) per garantire che il traffico multimediale venga assegnato in modo appropriato alle reti Wi-Fi.</p></li>
<li><p>Pianificare e ottimizzare le bande WiFi e il posizionamento dei punti di accesso. L'intervallo di 2,4 GHz può avere un'esperienza adeguata a seconda della posizione del punto di accesso, ma i punti di accesso sono spesso colpiti da altri dispositivi consumer che operano in tale intervallo. La gamma a 5 GHz è più adatta ai supporti in tempo reale a causa della sua gamma densa, ma richiede più punti di accesso per ottenere una copertura sufficiente. Gli endpoint devono inoltre supportare tale intervallo e essere configurati in base a tali bande.</p></li>
<li><p>Se si usano reti WiFi dual-band, è consigliabile implementare lo sterzo della banda. Lo <em>sterzo della banda</em> è una tecnica implementata dai fornitori di WiFi per influenzare i client dual-band in modo da usare l'intervallo a 5 GHz.</p></li>
<li><p>Quando i punti di accesso dello stesso canale sono troppo ravvicinati, possono causare sovrapposizioni di segnale e competere involontariamente, causando una cattiva esperienza per l'utente. Verificare che i punti di accesso adiacenti si trovino nei canali che non si sovrappongono.</p></li>
</ul>
<p>Ogni fornitore wireless ha le proprie raccomandazioni per la distribuzione della soluzione wireless. Consulta il fornitore di WiFi per indicazioni specifiche.</p></td>
</tr>
</tbody>
</table>

## <a name="bandwidth-requirements"></a>Requisiti di larghezza di banda

Teams è progettato per offrire la migliore esperienza di condivisione di audio, video e contenuti, indipendentemente dalle condizioni della rete. Ciò detto, quando la larghezza di banda è insufficiente, teams privilegia la qualità audio rispetto alla qualità video.

Se la larghezza di banda *non è* limitata, teams ottimizza la qualità multimediale, inclusi fino a risoluzione video 1080p, fino a 30fps per video e 15fps per il contenuto e audio ad alta fedeltà. 

[!INCLUDE [bandwidth-requirements](includes/bandwidth-requirements.md)]


## <a name="related-topics"></a>Argomenti correlati

[Principi di connettività di rete Microsoft 365 e Office 365](https://aka.ms/pnc)

[Endpoint mondiali: Skype for business online e teams](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

[Server proxy per Teams](proxy-servers-for-skype-for-business-online.md)

[Elementi multimediali in teams: perché le riunioni sono semplici](https://aka.ms/teams-media)

[Elementi multimediali in teams: Deep Dive in flussi multimediali](https://aka.ms/teams-media-flows)

[Modelli di identità e autenticazione in Teams](identify-models-authentication.md)

[Come implementare Teams](How-to-roll-out-teams.md)

[Risoluzione dei problemi di Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
