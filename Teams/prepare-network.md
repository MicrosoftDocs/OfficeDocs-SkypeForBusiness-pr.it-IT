---
title: Preparare la rete dell'organizzazione per Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: jastark, kojika
audience: admin
description: Informazioni sulla preparazione della rete delL’organizzazione per Microsoft Teams, tra cui requisiti di rete, ottimizzazione della rete e requisiti di larghezza di banda.
localization_priority: Priority
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
ms.openlocfilehash: db911db3631caebb0e767401f80c36bdac6c9c1b
ms.sourcegitcommit: f39484688800a3d22f361e660d0eeba974a44fb1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420831"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a>Preparare la rete dell'organizzazione per Microsoft Teams 

## <a name="network-requirements"></a>Requisiti di rete

Se la rete è già [ottimizzata per Microsoft 365 o Office 365](/Office365/Enterprise/assessing-network-connectivity), è probabile che sia pronta per Microsoft Teams. In ogni caso, e soprattutto se stai implementando rapidamente Teams come primo carico di lavoro di Microsoft 365 o Office 365 per supportare i **lavoratori remoti**, verifica quanto segue prima di iniziare a implementare Microsoft Teams:

1.  Le sedi della tua organizzazione hanno accesso a Internet (in modo che possano connettersi a Microsoft 365 o Office 365)? Oltre al normale traffico Web, verifica di aver aperto le porte TCP e gli indirizzi IP elencati per Teams negli [gli URL e gli intervalli di indirizzi IP di Office 365](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams).

    > [!IMPORTANT]
    > Se è necessario attuare la federazione con Skype for Business, sia locale che online, è necessario configurare un record DNS aggiuntivo.
    >
    >|Record DNS  |Servizio  |Protocol  |Priority  |Peso  |Port  |Target  |
    >|---------|---------|---------|---------|---------|---------|---------|
    >|SRV     |sipfederationtls     |TCP     |100     |1     |5061     |sipfed.online.lync.com     |
    
2.  Si dispone di un dominio verificato per Microsoft 365 o Office 365 (ad esempio, contoso.com)?
    
    - Se l’organizzazione non ha implementato Microsoft 365 o Office 365, consulta la [Guida introduttiva](/microsoft-365/admin/admin-overview/get-started-with-office-365).
    - Se l’organizzazione non ha aggiunto o configurato un dominio verificato per Microsoft 365 o Office 365, consulta le [Domande frequenti sui domini](/microsoft-365/admin/setup/domains-faq).

3.  L’organizzazione ha implementato Exchange Online e Microsoft SharePoint Online?
    
    - Se l’organizzazione non ha implementato Exchange Online, vedi [Informazioni su come interagiscono Exchange e Microsoft Teams](exchange-teams-interact.md).
    - Se l’organizzazione non ha implementato SharePoint Online, vedi [Informazioni su come Microsoft SharePoint Online e Microsoft OneDrive for Business interagiscono con Microsoft Teams](sharepoint-onedrive-interact.md).

Dopo aver verificato che i requisiti di rete siano soddisfatti, è possibile [implementare Microsoft Teams](./deploy-overview.md). Nel caso di una grande azienda multinazionale o se si riscontrano limitazioni di rete, leggere le informazioni su come valutare e ottimizzare la rete per Microsoft Teams.

> [!IMPORTANT]
> **Per gli istituti di istruzione**: se l’organizzazione è un istituto di istruzione e si utilizza un sistema informativo degli studenti (SIS), [implementare School Data Sync](/schooldatasync/) prima di implementare Microsoft Teams.
>  
> **Esecuzione in locale di Skype for Business Server**: se l'organizzazione esegue Skype for Business Server (o Lync Server) in locale, è necessario [configurare Azure AD Connect](/skypeforbusiness/hybrid/configure-azure-ad-connect) per sincronizzare la directory locale con Microsoft 365 o Microsoft Office 365.

### <a name="best-practice-monitor-your-network-using-cqd-and-call-analytics"></a>Procedura consigliata: monitorare la rete utilizzando Dashboard Qualità della chiamata e Analisi delle chiamate 

Utilizzare [Dashboard Qualità della chiamata (DQC)](turning-on-and-using-call-quality-dashboard.md) per ottenere informazioni dettagliate sulla qualità delle chiamate e delle riunioni in Microsoft Teams. DQC consente di ottimizzare la rete mantenendo sotto controllo la qualità, l’affidabilità e l’esperienza utente. DQC esamina la telemetria aggregata per un’intera organizzazione nella quale è possibile rilevare modelli generali che consentono di identificare i problemi e pianificare le correzioni. Inoltre, DQC fornisce report dettagliati sulle metriche per informazioni dettagliate sulla qualità, l’affidabilità e l’esperienza utente complessive. 

[Analisi delle chiamate](set-up-call-analytics.md) consente di indagare i problemi relativi alle chiamate e alle riunioni per un singolo utente.

## <a name="network-optimization"></a>Ottimizzazione della rete

Le attività seguenti sono facoltative e non sono necessarie per l’implementazione di Microsoft Teams, specialmente nel caso di una piccola azienda che ha già implementato Microsoft 365 o Microsoft Office 365. Attenersi a queste indicazioni per ottimizzare le prestazioni della rete e di Microsoft Teams o in caso di limitazioni di rete.

È consigliabile eseguire un’ulteriore ottimizzazione della rete se:

  - L’esecuzione di Microsoft Teams è lenta (ad esempio la larghezza di banda è insufficiente)
  - Le chiamate si interrompono (probabilmente a causa di blocchi del firewall o del proxy)
  - Si riscontrano interferenze o distorsioni durante le chiamate oppure riproduzioni audio robotiche (a causa di instabilità o perdita di pacchetti)

Per informazioni dettagliate sull’ottimizzazione della rete, incluse indicazioni per l’identificazione e la correzione di eventuali problemi di rete, consulta [Principi di connettività di rete di Microsoft 365 e Microsoft Office 365](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles).

<table>
<thead>
<tr class="header">
<th>Attività di ottimizzazione della rete</th>
<th>Dettagli</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Network Planner</td>
<td><p>Per ricevere assistenza nella valutazione della rete, nonché nei calcoli della larghezza di banda e nei requisiti di rete per le varie sedi dell’organizzazione, consulta lo strumento <a href="/microsoftteams/network-planner">Network Planner</a> nelll’<a href="https://admin.teams.microsoft.com">Interfaccia di amministrazione di Microsoft Teams</a>. Quando si specificano i dettagli della rete e l'uso di Teams, Network Planner calcola i requisiti di rete per la distribuzione di Teams e Cloud Voice nei luoghi fisici dell'organizzazione.</p>
<p>Per uno scenario di esempio, vedere <a href="/microsoftteams/tutorial-network-planner-example">Utilizzo di Network Planner, scenario di esempio</a>.</p></td>
</tr>
<tr class="even">
<td>Assistente per Teams</td>
<td><a href="/microsoftteams/use-advisor-teams-roll-out">Advisor per Teams</a> fa parte dell’<a href="https://admin.teams.microsoft.com">interfaccia di amministrazione di Microsoft Teams</a>. Valuta l'ambiente di Microsoft 365 o Office 365 e identifica le configurazioni più comuni che può essere necessario aggiornare o modificare prima che sia possibile implementare correttamente Teams.</td>
</tr>
<tr class="odd">
<td>Risoluzione del nome esterno</td>
<td>Assicurarsi che tutti i computer che eseguono il client Teams possano risolvere query DNS esterne per rilevare i servizi forniti da Microsoft 365 o Microsoft Office 365 e che il firewall non impedisca l’accesso. Per informazioni sulla configurazione delle porte del firewall, vai a <a href="/microsoftteams/office-365-urls-ip-address-ranges">URL e intervalli IP di Microsoft 365 e Microsoft Office 365</a>.</td>
</tr>
<tr class="odd">
<td>Salvataggio permanente della sessione</td>
<td>Verificare che il firewall non modifichi gli indirizzi NAT (Network Address Translation) o le porte mappate per UDP.</td>
</tr><tr class="odd">
<td>Convalidare le dimensioni del pool NAT</td>
<td>Convalidare le dimensioni del pool NAT necessarie per la connettività utente. Quando più utenti e dispositivi accedono a Microsoft 365 o Microsoft Office 365 utilizzando <a href="/office365/enterprise/nat-support-with-office-365">NAT (Network Address Translation) o PAT (Port Address Translation)</a>, è necessario assicurarsi che i dispositivi nascosti dietro ogni indirizzo IP instradabile pubblicamente non superino il numero supportato. Assicurarsi che ai pool NAT siano assegnati indirizzi IP pubblici adeguati per prevenire l'esaurimento della porta. L’esaurimento delle porte non consente agli utenti interni e ai dispositivi di connettersi al servizio Microsoft 365 o Microsoft Office 365.</td>
</tr>
<tr class="even">
<td>Routing ai data center Microsoft</td>
<td><a href="/office365/enterprise/client-connectivity">Implementare il routing ottimizzato ai data center Microsoft</a>. Identificare le posizioni che possono utilizzare i punti di uscita locali per connettersi alla rete Microsoft nel modo più efficiente possibile.</td>
</tr>
<tr class="odd">
<td>Indicazioni per il rilevamento e la prevenzione delle intrusioni</td>
<td>Se l’ambiente ha implementato un <a href="/azure/network-watcher/network-watcher-intrusion-detection-open-source-tools">Rilevamento intrusioni</a> o un sistema di prevenzione (IDS/IPS) per un livello di sicurezza supplementare per le connessioni in uscita, assicurarsi di autorizzare tutti gli URL di Microsoft 365 o Office 365.</td>
</tr>
<tr class="even">
<td>Configurare split tunneling per VPN</td>
<td><p>È consigliabile specificare un percorso alternativo per il traffico di Microsoft Teams che ignori la rete privata virtuale (VPN), comunemente nota come <a href="/windows/security/identity-protection/vpn/vpn-routing">Split tunnelling per VPN</a>. Lo split tunnelling per VPN consente di inviare il traffico di Microsoft 365 o Office 365 non alla VPN ma direttamente a Microsoft 365 o Office 365. Ignorare la VPN influisce positivamente sulla qualità di Microsoft Teams e riduce il carico nei dispositivi VPN e nella rete dell’organizzazione. Per implementare lo split tunneling per VPN, contatta il fornitore VPN.</p>
<p>Altri motivi per cui è consigliabile ignorare la VPN:
<ul>
<li><p>Le VPN in genere non sono progettate o configurate per supportare il traffico multimediale in tempo reale.</p></li> 
<li><p>È inoltre possibile che alcune VPN non supportino l’UDP (necessario per Microsoft Teams).</p></li> 
<li><p>Le VPN introducono anche un livello di crittografia aggiuntivo al traffico multimediale già crittografato.</p></li> 
<li><p>La connettività a Microsoft Teams potrebbe non essere efficiente a causa dell’hairpinning del traffico tramite un dispositivo VPN.</p></li></td>
</tr>
<tr class="odd">
<td>Implementare QoS</td>
<td><a href="/microsoftteams/qos-in-teams">Utilizzare il servizio QoS (Quality of Service)</a> per configurare la priorità dei pacchetti. In tal modo è possibile migliorare la qualità delle chiamate in Microsoft Teams nonché monitorare e risolvere i problemi relativi alla qualità delle chiamate. È necessario implementare QoS in tutti i segmenti di una rete gestita. Anche se per la larghezza di banda è stato eseguito un adeguato provisioning della rete, QoS consente la mitigazione dei rischi in caso di eventi di rete imprevisti. QoS assegna la priorità al traffico vocale in modo da impedire che eventi imprevisti influiscano negativamente sulla qualità.</td>
</tr>
<tr class="even">
<td>Ottimizzazione WiFi</td>
<td><p>Proprio come la VPN, le reti WiFi non sono necessariamente progettate o configurate per supportare il traffico multimediale in tempo reale. La pianificazione o l'ottimizzazione di una rete WiFi per supportare Microsoft Teams è una considerazione importante per una distribuzione di alta qualità. Prendere in considerazione questi fattori:</p>
<ul>
<li><p>Implementare QoS o Wi-Fi Multimedia (WMM) per garantire che il traffico multimediale abbia la priorità appropriata sulle reti Wi-Fi.</p></li>
<li><p>Pianificare e ottimizzare le bande Wi-Fi e il posizionamento del punto di accesso. L’intervallo a 2,4 GHz potrebbe offrire un’esperienza adeguata a seconda del posizionamento del punto di accesso. Tuttavia, i punti di accesso sono spesso influenzati da altri dispositivi di consumo che operano nell’intervallo. L'intervallo a 5 GHz è più adatto al traffico multimediale in tempo reale grazie al fitto intervallo ma richiede più punti di accesso per ottenere una copertura sufficiente. Gli endpoint devono inoltre supportare tale intervallo ed essere configurati per sfruttare tali bande di conseguenza.</p></li>
<li><p>Se si utilizzano reti WiFi dual band, prendere in considerazione l’implementazione del band steering. <em>Il band steering</em> è una tecnica implementata dai fornitori di reti WiFi per influenzare i client dual band a utilizzare l'intervallo a 5 GHz.</p></li>
<li><p>Quando i punti di accesso dello stesso canale sono troppo vicini tra loro, possono causare la sovrapposizione del segnale e competere involontariamente, causando una brutta esperienza per l'utente. Assicurarsi che i punti di accesso che si trovano uno accanto all'altro siano su canali che non si sovrappongono.</p></li>
</ul>
<p>Ogni fornitore wireless ha le proprie raccomandazioni per l'implementazione della propria soluzione wireless. Per indicazioni specifiche, contattare il fornitore della rete WiFi.</p></td>
</tr>
</tbody>
</table>

## <a name="bandwidth-requirements"></a>Requisiti relativi alla larghezza di banda

Microsoft Teams è progettato per offrire esperienze audio, video e di condivisione contenuti eccezionali, a prescindere dalle condizioni di rete. Tuttavia, se la larghezza di banda è insufficiente, Microsoft Teams assegna la priorità alla qualità audio sulla qualità video.

Se la larghezza di banda non è limitata, Microsoft Teams ottimizza la qualità multimediale, audio di alta fedeltà, inclusa una risoluzione video massima di 1080p, fino a 30fps (fotogrammi al secondo) per video e contenuto.

Questa tabella descrive le modalità di utilizzo della larghezza di banda da parte di Teams. Teams fa un utilizzo moderato della larghezza di banda ed è in grado di garantire una qualità video ad alta definizione in meno di 1,5 Mbps. Il consumo effettivo della larghezza di banda in ogni chiamata audio/video o riunione varia in base a diversi fattori, ad esempio il layout video, la risoluzione video e i fotogrammi video al secondo. Quando sarà disponibile una maggiore larghezza di banda, la qualità e l'utilizzo aumenteranno per offrire la migliore esperienza.

:::row:::
   :::column span="":::
      **Modalità**
   :::column-end:::
   :::column span="3":::
      **Requisiti di larghezza di banda (bitrate KB/s su/giù)**
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
   :::column-end:::
   :::column span="":::
      **Minimo**
   :::column-end:::
   :::column span="":::
      **Consigliata**
   :::column-end:::
   :::column span="":::
      **Prestazioni ottimali**
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="4":::
      **Audio**
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        Uno a uno
   :::column-end:::
   :::column span="":::
        10/10
   :::column-end:::
   :::column span="":::
        58/58
   :::column-end:::
   :::column span="":::
        76/76
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        Riunioni
   :::column-end:::
   :::column span="":::
        10/10
   :::column-end:::
   :::column span="":::
        58/58
   :::column-end:::
   :::column span="":::
        76/76
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="4":::
      **Video**
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        Uno a uno
   :::column-end:::
   :::column span="":::
        150/150
   :::column-end:::
   :::column span="":::
        1,500/1,500
   :::column-end:::
   :::column span="":::
        4,000/4,000
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        Riunioni
   :::column-end:::
   :::column span="":::
        150/200
   :::column-end:::
   :::column span="":::
        2,500/4,000
   :::column-end:::
   :::column span="":::
        4,000/4,000
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="4":::
      **Condivisione dello schermo.**
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        Uno a uno
   :::column-end:::
   :::column span="":::
        200/200
   :::column-end:::
   :::column span="":::
        1,500/1,500
   :::column-end:::
   :::column span="":::
        4,000/4,000
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        Riunioni
   :::column-end:::
   :::column span="":::
        250/250
   :::column-end:::
   :::column span="":::
        2,500/2,500
   :::column-end:::
   :::column span="":::
        4,000/4,000
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="4":::
      **Modalità Insieme**
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        Uno a uno
   :::column-end:::
   :::column span="":::
        N/D
   :::column-end:::
   :::column span="":::
        N/D
   :::column-end:::
   :::column span="":::
        N/D
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
        Riunioni
   :::column-end:::
   :::column span="":::
        1,000/1,500
   :::column-end:::
   :::column span="":::
        1,500/2,500
   :::column-end:::
   :::column span="":::
        2,500/4,000
   :::column-end:::
:::row-end:::

I requisiti **minimi**, **consigliati** e **le prestazioni migliori** della larghezza di banda sono basati sull'utilizzo per endpoint. In genere, è presente un endpoint per utente, come un computer o un dispositivo mobile. Tuttavia, se un utente partecipa a una riunione di Teams in *sia* un computer *che* un dispositivo mobile, a tale utente vengono associati due endpoint.

- I requisiti **minimi** della larghezza di banda per le videochiamate sono fino a una risoluzione di 240p, la frequenza dei fotogrammi del contenuto di condivisione dello schermo adattiva da 1,875 a 7,5 fps e i video in modalità Insieme/Raccolta grande fino a una risoluzione di 540p.  

- I requisiti **consigliati** per la larghezza di banda per le videochiamate sono fino a 1080p di risoluzione<sup>\*</sup>, frequenza dei fotogrammi del contenuto di condivisione dello schermo adattivi da 7,5 a 30 fps e video in modalità Insieme/Raccolta grande fino a una risoluzione di 1080p<sup>\*</sup>.  

- **Prestazioni ottimali** Guidance consente una maggiore fedeltà di video per riunioni con partecipanti di grandi dimensioni, ambienti con perdita elevata e contenuti di movimento più elevati con frequenze dei fotogrammi del contenuto di condivisione dello schermo adattive da 15 a 30 fps.

<sup>\*</sup>È prevista una qualità fino a 1080p, ma a seconda delle condizioni della rete, la risoluzione e la qualità del video verranno ottimizzate di conseguenza.  

## <a name="related-topics"></a>Argomenti correlati

[Principi di connettività di rete di Microsoft 365 e Office 365](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)

[Endpoint in tutto il mondo: Skype for Business Online e Microsoft Teams](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)

[Server proxy per Teams](proxy-servers-for-skype-for-business-online.md)

[Elementi multimediali di Teams: ciò che rende le riunioni così semplici](https://aka.ms/teams-media)

[Elementi multimediali di Teams: un approfondimento sui flussi multimediali](https://aka.ms/teams-media-flows)

[Modelli di identità e autenticazione in Teams](identify-models-authentication.md)

[Come implementare Teams](./deploy-overview.md)

[Risoluzione dei problemi di Teams](/MicrosoftTeams/troubleshoot/teams)
