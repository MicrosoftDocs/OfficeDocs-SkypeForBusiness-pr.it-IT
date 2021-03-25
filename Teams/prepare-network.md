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
ms.openlocfilehash: 1c84a753146899011fa34be56e0746cc0c600b31
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117754"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a>Preparare la rete dell'organizzazione per Microsoft Teams 

## <a name="network-requirements"></a>Requisiti di rete

Se la rete è già stata ottimizzata per [Microsoft 365 o Office 365,](/Office365/Enterprise/assessing-network-connectivity)probabilmente si è pronti per Microsoft Teams. In ogni caso, e soprattutto se si sta stendando Rapidamente Teams come primo carico di lavoro di Microsoft 365 o Office 365 per supportare i lavoratori **remoti,** verificare quanto segue prima di iniziare l'implementazione di Teams:

1.  Tutte le posizioni hanno accesso a Internet (in modo che possano connettersi a Microsoft 365 o Office 365)? Almeno, oltre al normale traffico Web, assicurati di aver aperto quanto segue, per tutte le posizioni, per i file multimediali in Teams:

    |  |  |
    |---------|---------|
    |Porte     |Porte UDP <strong>da 3478</strong> a <strong>3481</strong>        |
    |[Indirizzi IP](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) |<strong>13.107.64.0/18,</strong> <strong>52.112.0.0/14</strong>e <strong>52.120.0.0/14</strong>         |

    > [!IMPORTANT]
    > Se è necessario eseguire la federazione con Skype for Business, locale o online, è necessario configurare alcuni record DNS aggiuntivi.
    >
    >|Record CNAME /Nome host  |TTL  |Punta all'indirizzo o al valore  |
    >|---------|---------|---------|
    >|sip     |    3600     |    sipdir.online.lync.com     |
    >|lyncdiscover     |   3600      |    webdir.online.lync.com     |
    
2.  Si ha un dominio verificato per Microsoft 365 o Office 365 (ad esempio, contoso.com)?
    
    - Se l'organizzazione non ha eseguito l'implementazione di Microsoft 365 o Office 365, vedere [Introduzione.](/microsoft-365/admin/admin-overview/get-started-with-office-365)
    - Se l'organizzazione non ha aggiunto o configurato un dominio verificato per Microsoft 365 o Office 365, vedere le domande [frequenti sui domini.](/microsoft-365/admin/setup/domains-faq)

3.  L'organizzazione ha distribuito Exchange Online e SharePoint Online?
    
    - Se l'organizzazione non ha Exchange Online, vedere Informazioni [sull'interazione tra Exchange e Microsoft Teams.](exchange-teams-interact.md)
    - Se l'organizzazione non ha SharePoint Online, vedere Informazioni sull'interazione tra SharePoint Online e [OneDrive for Business con Microsoft Teams.](sharepoint-onedrive-interact.md)

Dopo aver verificato che soddisfi questi requisiti di rete, potresti essere pronto per [l'implementazione di Teams.](./deploy-overview.md) Se si è un'azienda multinazionale di grandi dimensioni o se si sa di avere alcune limitazioni di rete, leggere per informazioni su come valutare e ottimizzare la rete per Teams.

> [!IMPORTANT]
> **Per gli istituti di** istruzione: se l'organizzazione è un istituto di istruzione e si usa un sistema SIS [(Student](/schooldatasync/) Information System), distribuire School Data Sync prima di distribuire Teams.
>  
> Esecuzione di **Skype for Business Server** locale: se l'organizzazione esegue Skype for Business Server locale (o Lync Server), è necessario configurare Azure AD [Connect](/skypeforbusiness/hybrid/configure-azure-ad-connect) per sincronizzare la directory locale con Microsoft 365 o Office 365.

### <a name="best-practice-monitor-your-network-using-cqd-and-call-analytics"></a>Procedura consigliata: monitorare la rete usando CQD e l'analisi delle chiamate 

Usa il [call quality dashboard (CQD)](turning-on-and-using-call-quality-dashboard.md) per ottenere informazioni approfondite sulla qualità delle chiamate e delle riunioni in Teams. CQD consente di ottimizzare la rete tenendo sotto controllo la qualità, l'affidabilità e l'esperienza utente. CQD esamina la telemetria aggregata per un'intera organizzazione in cui i modelli complessivi possono diventare evidenti, il che consente di identificare i problemi e pianificare le correzioni. Inoltre, CQD fornisce report dettagliati sulle metriche che forniscono informazioni generali sulla qualità, l'affidabilità e l'esperienza utente. 

Si userà [l'analisi delle chiamate](set-up-call-analytics.md) per esaminare i problemi di chiamata e riunione per un singolo utente.

## <a name="network-optimization"></a>Ottimizzazione della rete

Le attività seguenti sono facoltative e non sono necessarie per la distribuzione di Teams, soprattutto se si è una piccola azienda e si è già eseguito l'implementazione di Microsoft 365 o Office 365. Usare queste indicazioni per ottimizzare le prestazioni della rete e di Teams o se si sa di avere alcune limitazioni di rete.

È consigliabile eseguire un'ulteriore ottimizzazione della rete se:

  - Teams viene eseguito lentamente (forse la larghezza di banda non è sufficiente)
  - Le chiamate continuano a essere in uscita (potrebbe essere dovuto a firewall o proxy blocker)
  - Le chiamate sono statiche e tagliate o le voci suonano come robot (potrebbe essere instabilità o perdita di pacchetti)

Per una discussione approfondita sull'ottimizzazione della rete, incluse indicazioni per l'identificazione e la correzione di problemi di rete, vedere Principi di connettività di rete di [Microsoft 365 e Office 365.](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)

<table>
<thead>
<tr class="header">
<th><strong>Attività di ottimizzazione della rete</strong></th>
<th><strong>Dettagli</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Network Planner</td>
<td><p>Per informazioni sulla valutazione della rete, inclusi i calcoli della larghezza di banda e i requisiti di rete nelle posizioni fisiche dell'organizzazione, vedere lo strumento <a href="/microsoftteams/network-planner">Network Planner</a> nell'interfaccia di amministrazione <a href="https://admin.teams.microsoft.com">di Teams.</a> Quando si forniscono i dettagli della rete e l'utilizzo di Teams, Network Planner calcola i requisiti di rete per la distribuzione di Teams e della voce cloud nelle posizioni fisiche dell'organizzazione.</p>
<p>Per uno scenario di esempio, vedere <a href="/microsoftteams/tutorial-network-planner-example">Uso di Network Planner - scenario di esempio.</a></p></td>
</tr>
<tr class="even">
<td>Advisor per Teams</td>
<td><a href="/microsoftteams/use-advisor-teams-roll-out">Advisor per Teams</a> fa parte dell'interfaccia <a href="https://admin.teams.microsoft.com">di amministrazione di Teams.</a> Valuta l'ambiente di Microsoft 365 o Office 365 e identifica le configurazioni più comuni che può essere necessario aggiornare o modificare prima che sia possibile implementare correttamente Teams.</td>
</tr>
<tr class="odd">
<td>Risoluzione dei nomi esterni</td>
<td>Assicurarsi che tutti i computer che eseguono il client Teams possano risolvere le query DNS esterne per individuare i servizi forniti da Microsoft 365 o Office 365 e che i firewall non impedino l'accesso. Per informazioni sulla configurazione delle porte del firewall, vedere URL e intervalli IP di <a href="/microsoftteams/office-365-urls-ip-address-ranges">Microsoft 365 e Office 365.</a></td>
</tr>
<tr class="odd">
<td>Mantenere la persistenza della sessione</td>
<td>Assicurarsi che il firewall non cambi gli indirizzi o le porte NAT (Network Address Translation) mappati per UDP.</td>
</tr><tr class="odd">
<td>Convalidare le dimensioni del pool NAT</td>
<td>Convalidare le dimensioni del pool NAT (Network Address Translation) necessarie per la connettività degli utenti. Quando più utenti e dispositivi accedono a Microsoft 365 o Office 365 con <a href="/office365/enterprise/nat-support-with-office-365">NAT (Network Address Translation) o PAT (Port Address Translation),</a>è necessario assicurarsi che i dispositivi nascosti dietro ogni indirizzo IP pubblicamente instradabile non superino il numero supportato. Assicurarsi che ai pool NAT siano assegnati indirizzi IP pubblici adeguati per evitare l'esaurimento delle porte. L'esaurimento delle porte contribuirà a consentire agli utenti e ai dispositivi interni di connettersi al servizio Microsoft 365 o Office 365.</td>
</tr>
<tr class="even">
<td>Routing ai data center Microsoft</td>
<td><a href="/office365/enterprise/client-connectivity">Implementare il routing più efficiente ai data center Microsoft.</a> Identificare le posizioni che possono usare i punti di uscita locali o locali per connettersi alla rete Microsoft nel modo più efficiente possibile.</td>
</tr>
<tr class="odd">
<td>Indicazioni per il rilevamento e la prevenzione delle intrusioni</td>
<td>Se nell'ambiente <a href="/azure/network-watcher/network-watcher-intrusion-detection-open-source-tools"></a> è distribuito un sistema di rilevamento o prevenzione delle intrusioni (IDS/IPS) per un ulteriore livello di sicurezza per le connessioni in uscita, assicurarsi di consentire tutti gli URL di Microsoft 365 o Office 365.</td>
</tr>
<tr class="even">
<td>Configurare la VPN a tunnel diviso</td>
<td><p>È consigliabile specificare un percorso alternativo per il traffico di Teams che ignora la rete privata virtuale (VPN), comunemente nota come <a href="/windows/security/identity-protection/vpn/vpn-routing">VPN a tunnel diviso.</a> Il tunneling diviso significa che il traffico per Microsoft 365 o Office 365 non passa attraverso la VPN, ma passa direttamente a Microsoft 365 o Office 365. L'esclusione della VPN avrà un impatto positivo sulla qualità di Teams e riduce il carico dai dispositivi VPN e dalla rete dell'organizzazione. Per implementare una VPN a tunnel diviso, collaborare con il fornitore della VPN.</p>
<p>Altri motivi per cui è consigliabile ignorare la VPN:
<ul>
<li><p>Le RETI VPN in genere non sono progettate o configurate per supportare supporti multimediali in tempo reale.</p></li> 
<li><p>Alcune VPN potrebbero anche non supportare UDP (obbligatorio per Teams).</p></li> 
<li><p>Le VPN introducono anche un ulteriore livello di crittografia sul traffico multimediale già crittografato.</p></li> 
<li><p>La connettività a Teams potrebbe non essere efficiente a causa del traffico che blocca i capelli attraverso un dispositivo VPN.</p></li></td>
</tr>
<tr class="odd">
<td>Implementare QoS</td>
<td><a href="/microsoftteams/qos-in-teams">Usare la qualità del servizio (QoS)</a> per configurare la priorità dei pacchetti. Questo migliorerà la qualità delle chiamate in Teams e ti aiuterà a monitorare e risolvere i problemi relativi alla qualità delle chiamate. La QoS deve essere implementata in tutti i segmenti di una rete gestita. Anche quando è stato eseguito il provisioning adeguato di una rete per la larghezza di banda, QoS fornisce una riduzione dei rischi in caso di eventi di rete imprevisti. Con QoS, il traffico vocale è prioritario in modo che questi eventi imprevisti non influiscano negativamente sulla qualità.</td>
</tr>
<tr class="even">
<td>Ottimizza WiFi</td>
<td><p>Analogamente alla VPN, le reti WiFi non sono necessariamente progettate o configurate per supportare supporti multimediali in tempo reale. La pianificazione o l'ottimizzazione di una rete WiFi per supportare Teams è una considerazione importante per una distribuzione di alta qualità. Considerare questi fattori:</p>
<ul>
<li><p>Implementare QoS o WiFi Multimedia (WMM) per garantire che il traffico multimediale sia classificato in modo appropriato sulle reti WiFi.</p></li>
<li><p>Pianificare e ottimizzare le bande WiFi e il posizionamento dei punti di accesso. L'intervallo di 2,4 GHz potrebbe offrire un'esperienza adeguata a seconda del posizionamento del punto di accesso, ma i punti di accesso sono spesso interessati da altri dispositivi consumer che operano in tale intervallo. L'intervallo di 5 GHz è più adatto ai supporti multimediali in tempo reale a causa della sua fitta gamma, ma richiede più punti di accesso per ottenere una copertura sufficiente. Gli endpoint devono inoltre supportare tale intervallo e devono essere configurati per sfruttare di conseguenza tali bande.</p></li>
<li><p>Se si usano reti WiFi a banda doppia, valutare l'implementazione dello sterzo a banda. <em>Lo sterzo</em> a banda è una tecnica implementata dai fornitori WiFi per influenzare i client a banda doppia per l'uso dell'intervallo di 5 GHz.</p></li>
<li><p>Quando i punti di accesso dello stesso canale sono troppo vicini tra loro, possono causare la sovrapposizione del segnale e competere involontariamente, causando un'esperienza negativa per l'utente. Assicurarsi che i punti di accesso uno accanto all'altro siano su canali che non si sovrappongono.</p></li>
</ul>
<p>Ogni fornitore wireless ha i propri consigli per la distribuzione della soluzione wireless. Per indicazioni specifiche, rivolgersi al fornitore del WiFi.</p></td>
</tr>
</tbody>
</table>

## <a name="bandwidth-requirements"></a>Requisiti di larghezza di banda

Teams è progettato per offrire la migliore esperienza di condivisione di contenuti, video e audio indipendentemente dalle condizioni di rete. Detto questo, quando la larghezza di banda è insufficiente, Teams assegna priorità alla qualità audio rispetto alla qualità video.

Se  la larghezza di banda non è limitata, Teams ottimizza la qualità dei contenuti multimediali, inclusa la risoluzione video fino a 1080p, fino a 30fps per video e 15fps per i contenuti e audio ad alta fedeltà. 

[!INCLUDE [bandwidth-requirements](includes/bandwidth-requirements.md)]


## <a name="related-topics"></a>Argomenti correlati

[Principi di connettività di rete di Microsoft 365 e Office 365](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)

[Endpoint in tutto il mondo: Skype for Business Online e Teams](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

[Server proxy per Teams](proxy-servers-for-skype-for-business-online.md)

[Elementi multimediali in Teams: Perché le riunioni sono semplici](https://aka.ms/teams-media)

[Elementi multimediali in Teams: Approfondimento sui flussi multimediali](https://aka.ms/teams-media-flows)

[Modelli di identità e autenticazione in Teams](identify-models-authentication.md)

[Come implementare Teams](./deploy-overview.md)

[Risoluzione dei problemi di Teams](/MicrosoftTeams/troubleshoot/teams)