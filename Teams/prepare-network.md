---
title: Preparare la rete dell'organizzazione per Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: jastark, kojika
audience: admin
description: Informazioni sulla preparazione della rete dell'organizzazione per Microsoft Teams, inclusi i requisiti di rete, l'ottimizzazione della rete e i requisiti di larghezza di banda.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365initiative-deployteams
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom:
- seo-marvel-mar2020
ms.openlocfilehash: 9212c096323eb57754e0a8a47b61649bec42de87
ms.sourcegitcommit: 5c33ca450a3215b9bf3c5da8bb3c9ef1a715a1a2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2021
ms.locfileid: "50099573"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a>Preparare la rete dell'organizzazione per Microsoft Teams 

## <a name="network-requirements"></a>Requisiti di rete

Se la rete è già stata ottimizzata per [Microsoft 365 o Office 365,](https://docs.microsoft.com/Office365/Enterprise/assessing-network-connectivity)probabilmente si è pronti per Microsoft Teams. In ogni caso, e in particolare se si sta stendando Rapidamente Teams come primo carico di lavoro di Microsoft 365 o Office 365 per supportare i lavoratori **remoti,** controllare quanto segue prima di iniziare l'implementazione di Teams:

1.  Tutte le posizioni hanno accesso a Internet (in modo che possano connettersi a Microsoft 365 o Office 365)? Almeno, oltre al normale traffico Web, assicurati di aver aperto quanto segue, per tutte le posizioni, per i file multimediali in Teams:

    |  |  |
    |---------|---------|
    |Porte     |Porte UDP <strong>da 3478</strong> a <strong>3481</strong>        |
    |[Indirizzi IP](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) |<strong>13.107.64.0/18,</strong> <strong>52.112.0.0/14</strong>e <strong>52.120.0.0/14</strong>         |

    > [!IMPORTANT]
    > Se è necessario eseguire la federazione con Skype for Business, in locale o online, è necessario configurare alcuni record DNS aggiuntivi.
    >
    >|CNAME Records /Host name  |TTL  |Indirizzo o valore di puntamento  |
    >|---------|---------|---------|
    >|sip     |    3600     |    sipdir.online.lync.com     |
    >|lyncdiscover     |   3600      |    webdir.online.lync.com     |
    
2.  Si ha un dominio verificato per Microsoft 365 o Office 365 (ad esempio, contoso.com)?
    
    - Se l'organizzazione non ha ancora eseguito l'implementazione di Microsoft 365 o Office 365, vedere [Introduzione.](https://docs.microsoft.com/microsoft-365/admin/admin-overview/get-started-with-office-365)
    - Se l'organizzazione non ha aggiunto o configurato un dominio verificato per Microsoft 365 o Office 365, vedere le [domande frequenti sui domini.](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)

3.  L'organizzazione ha distribuito Exchange Online e SharePoint Online?
    
    - Se l'organizzazione non ha Exchange Online, vedere Informazioni [sull'interazione tra Exchange e Microsoft Teams.](exchange-teams-interact.md)
    - Se l'organizzazione non ha SharePoint Online, vedere Informazioni sull'interazione tra SharePoint Online e [OneDrive for Business con Microsoft Teams.](sharepoint-onedrive-interact.md)

Dopo aver verificato che i requisiti di rete siano soddisfatti, si può essere pronti per [l'implementazione di Teams.](How-to-roll-out-teams.md) Se si è una grande multinazionale o se si è certi di avere alcune limitazioni di rete, leggere per informazioni su come valutare e ottimizzare la rete per Teams.

> [!IMPORTANT]
> **Per gli istituti di** istruzione: se l'organizzazione è un istituto di istruzione e si usa un sistema SIS [(Student](https://docs.microsoft.com/schooldatasync/) Information System), distribuire School Data Sync prima di implementare Teams.
>  
> **Esecuzione** di Skype for Business Server locale: se l'organizzazione esegue Skype for Business Server (o Lync Server) locale, è necessario configurare [Azure AD Connect](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-azure-ad-connect) per sincronizzare la directory locale con Microsoft 365 o Office 365.

### <a name="best-practice-monitor-your-network-using-cqd-and-call-analytics"></a>Procedura consigliata: Monitorare la rete usando Call Analytics e Call Analytics 

Usa [Call Quality Dashboard (CQD)](turning-on-and-using-call-quality-dashboard.md) per ottenere informazioni approfondite sulla qualità delle chiamate e delle riunioni in Teams. CQD consente di ottimizzare la rete tenendo sotto controllo la qualità, l'affidabilità e l'esperienza utente. CQD esamina la telemetria aggregata per un'intera organizzazione in cui possono presentarsi modelli generali, che consentono di identificare i problemi e pianificare le correzioni. Inoltre, CQD fornisce report dettagliati sulle metriche che forniscono informazioni approfondite su qualità generale, affidabilità ed esperienza utente. 

Userai [l'analisi delle chiamate per](set-up-call-analytics.md) esaminare i problemi di chiamata e di riunione per un singolo utente.

## <a name="network-optimization"></a>Ottimizzazione della rete

Le attività seguenti sono facoltative e non sono necessarie per l'implementazione di Teams, soprattutto se si è una piccola azienda e si è già eseguito l'implementazione di Microsoft 365 o Office 365. Usare queste indicazioni per ottimizzare le prestazioni di rete e Teams o se si è certi di avere alcune limitazioni di rete.

È consigliabile eseguire un'ottimizzazione di rete aggiuntiva se:

  - Teams viene eseguito lentamente (probabilmente la larghezza di banda non è sufficiente)
  - L'eliminazione delle chiamate potrebbe essere dovuta al blocco del firewall o del proxy.
  - Le chiamate hanno effetti statici ed esigo, o voci che suonano come i robot (potrebbe essere instabilità o perdita di pacchetti)

Per una discussione approfondita sull'ottimizzazione di rete, incluse le indicazioni per identificare e correggere i problemi di rete, leggere i principi della connettività di rete di [Microsoft 365 e Office 365.](https://aka.ms/pnc)

<table>
<thead>
<tr class="header">
<th><strong>Attività di ottimizzazione di rete</strong></th>
<th><strong>Dettagli</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Pianificazione della rete</td>
<td><p>Per una valutazione della rete, inclusi calcoli della larghezza di banda e requisiti di rete nelle posizioni fisiche dell'organizzazione, consultare lo strumento <a href="https://docs.microsoft.com/microsoftteams/network-planner">Network Planner</a> nell'interfaccia di amministrazione <a href="https://admin.teams.microsoft.com">di Teams.</a> Quando fornisci i dettagli della rete e l'utilizzo di Teams, Network Planner calcola i requisiti di rete per la distribuzione di Teams e della voce sul cloud nelle posizioni fisiche della tua organizzazione.</p>
<p>Per uno scenario di esempio, vedere <a href="https://docs.microsoft.com/microsoftteams/tutorial-network-planner-example">Uso di Network Planner - scenario di esempio.</a></p></td>
</tr>
<tr class="even">
<td>Consulente per Teams</td>
<td><a href="https://docs.microsoft.com/microsoftteams/use-advisor-teams-roll-out">Advisor per Teams fa</a> parte dell'interfaccia <a href="https://admin.teams.microsoft.com">di amministrazione di Teams.</a> Valuta l'ambiente di Microsoft 365 o Office 365 e identifica le configurazioni più comuni che può essere necessario aggiornare o modificare prima che sia possibile implementare correttamente Teams.</td>
</tr>
<tr class="odd">
<td>Risoluzione dei nomi esterni</td>
<td>Assicurarsi che tutti i computer che eseguono il client Teams possano risolvere le query DNS esterne per individuare i servizi forniti da Microsoft 365 o Office 365 e che i firewall non impedino l'accesso. Per informazioni sulla configurazione delle porte del firewall, accedere agli URL e agli intervalli IP di <a href="https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges">Microsoft 365 e Office 365.</a></td>
</tr>
<tr class="odd">
<td>Mantenere la persistenza della sessione</td>
<td>Assicurati che il firewall non cambi gli indirizzi NAT (Network Address Translation) o le porte per UDP.</td>
</tr><tr class="odd">
<td>Verificare le dimensioni del pool NAT</td>
<td>Verificare le dimensioni del pool NAT (Network Address Translation) necessarie per la connettività degli utenti. Quando più utenti e dispositivi accedono a Microsoft 365 o Office 365 con <a href="https://docs.microsoft.com/office365/enterprise/nat-support-with-office-365">NAT (Network Address Translation) o PAT (Port Address Translation),</a>è necessario assicurarsi che i dispositivi nascosti da ogni indirizzo IP instradabile pubblicamente non superino il numero supportato. Assicurarsi che ai pool di NAT siano assegnati adeguati indirizzi IP pubblici per evitare l'esaurimento delle porte. L'esaurimento delle porte contribuirà agli utenti interni e ai dispositivi che non riescono a connettersi al servizio Microsoft 365 o Office 365.</td>
</tr>
<tr class="even">
<td>Routing a data center Microsoft</td>
<td><a href="https://docs.microsoft.com/office365/enterprise/client-connectivity">Implementare il routing più efficiente verso data center Microsoft.</a> Identificare le posizioni che possono usare i punti di uscita locali o locali per connettersi alla rete Microsoft nel modo più efficiente possibile.</td>
</tr>
<tr class="odd">
<td>Indicazioni per il rilevamento e la prevenzione delle intrusioni</td>
<td>Se nell'ambiente è distribuito un sistema di rilevamento o prevenzione delle <a href="https://docs.microsoft.com/azure/network-watcher/network-watcher-intrusion-detection-open-source-tools">intrusioni</a> (IDS/IPS) per un ulteriore livello di sicurezza per le connessioni in uscita, assicurarsi di consentire tutti gli URL di Microsoft 365 o Office 365.</td>
</tr>
<tr class="even">
<td>Configurare VPN split tunnel</td>
<td><p>È consigliabile fornire un percorso alternativo per il traffico di Teams che bypassa la rete privata virtuale (VPN), comunemente nota come <a href="https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-routing">VPN split tunnel.</a> Lo split tunneling significa che il traffico per Microsoft 365 o Office 365 non passa attraverso la VPN, ma passa direttamente a Microsoft 365 o Office 365. Ignorare la VPN avrà un impatto positivo sulla qualità di Teams e riduce il carico dai dispositivi VPN e dalla rete dell'organizzazione. Per implementare una VPN split tunnel, collaborare con il proprio fornitore di VPN.</p>
<p>Altri motivi per cui è consigliabile ignorare la VPN:
<ul>
<li><p>Le VPN in genere non sono progettate o configurate per supportare elementi multimediali in tempo reale.</p></li> 
<li><p>Alcune VPN potrebbero anche non supportare UDP (necessario per Teams).</p></li> 
<li><p>Le VPN introducono anche un ulteriore livello di crittografia sul traffico multimediale già crittografato.</p></li> 
<li><p>La connettività a Teams potrebbe non essere efficiente a causa del traffico che gira i capelli attraverso un dispositivo VPN.</p></li></td>
</tr>
<tr class="odd">
<td>Implementare QoS</td>
<td><a href="https://docs.microsoft.com/microsoftteams/qos-in-teams">Usare la qualità del servizio (QoS, Quality of Service)</a> per configurare la priorità dei pacchetti. Ciò migliorerà la qualità delle chiamate in Teams e ti aiuterà a monitorare e risolvere i problemi relativi alla qualità delle chiamate. La QoS deve essere implementata in tutti i segmenti di una rete gestita. Anche quando è stato adeguatamente effettuato il provisioning di una rete per la larghezza di banda, QoS fornisce una attenuazione dei rischi in caso di eventi imprevisti di rete. Con la QoS, il traffico vocale è prioritario in modo che questi eventi imprevisti non influiscano negativamente sulla qualità.</td>
</tr>
<tr class="even">
<td>Ottimizza WiFi</td>
<td><p>Come nelle VPN, le reti WiFi non sono necessariamente progettate o configurate per supportare supporti multimediali in tempo reale. La pianificazione o l'ottimizzazione di una rete WiFi per supportare Teams è un aspetto importante per una distribuzione di alta qualità. Tenere presenti questi fattori:</p>
<ul>
<li><p>Implementare QoS o WiFi Multimedia (WMM) per garantire che il traffico multimediale sia prioritario in modo appropriato rispetto alle reti WiFi.</p></li>
<li><p>Pianificare e ottimizzare le bande WiFi e il posizionamento dei punti di accesso. L'intervallo da 2,4 GHz potrebbe offrire un'esperienza adeguata a seconda del posizionamento del punto di accesso, ma i punti di accesso sono spesso interessati da altri dispositivi consumer che operano in tale intervallo. L'intervallo da 5 GHz è più adatto per supporti multimediali in tempo reale a causa della sua fitta gamma, ma richiede più punti di accesso per ottenere una copertura sufficiente. Gli endpoint devono inoltre supportare tale intervallo ed essere configurati per sfruttare tali bande di conseguenza.</p></li>
<li><p>Se si usano reti WiFi a banda doppia, valutare l'implementazione di una band che esemersi. <em>La formazione a bande</em> è una tecnica implementata dai fornitori wi-fi per influenzare i client a banda doppia per l'utilizzo dell'intervallo da 5 GHz.</p></li>
<li><p>Quando i punti di accesso dello stesso canale sono troppo vicini tra loro, possono causare la sovrapposizione del segnale e competere involontariamente, causando una cattiva esperienza per l'utente. Assicurarsi che i punti di accesso uno accanto all'altro siano presenti in canali che non si sovrappongono.</p></li>
</ul>
<p>Ogni fornitore di dispositivi wireless ha i propri suggerimenti per la distribuzione della soluzione wireless. Per istruzioni specifiche, rivolgersi al fornitore del WiFi.</p></td>
</tr>
</tbody>
</table>

## <a name="bandwidth-requirements"></a>Requisiti di larghezza di banda

Teams è progettato per offrire la migliore esperienza audio, video e condivisione di contenuti indipendentemente dalle condizioni di rete. Tuttavia, quando la larghezza di banda è insufficiente, Teams assegna priorità alla qualità audio rispetto alla qualità video.

Laddove  la larghezza di banda non è limitata, Teams ottimizza la qualità multimediale, fino a una risoluzione video di 1080 p, fino a 30fps per i video e 15fps per i contenuti e audio ad alta fedeltà. 

[!INCLUDE [bandwidth-requirements](includes/bandwidth-requirements.md)]


## <a name="related-topics"></a>Argomenti correlati

[Principi della connettività di rete di Microsoft 365 e Office 365](https://aka.ms/pnc)

[Endpoint internazionali: Skype for Business Online e Teams](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

[Server proxy per Teams](proxy-servers-for-skype-for-business-online.md)

[Elementi multimediali in Teams: Perché le riunioni sono semplici](https://aka.ms/teams-media)

[Elementi multimediali in Teams: approfondimento sui flussi multimediali](https://aka.ms/teams-media-flows)

[Modelli di identità e autenticazione in Teams](identify-models-authentication.md)

[Come implementare Teams](How-to-roll-out-teams.md)

[Risoluzione dei problemi di Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
