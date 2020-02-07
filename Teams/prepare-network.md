---
title: Preparare la rete dell'organizzazione per Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/25/2019
ms.topic: reference
ms.service: msteams
ms.reviewer: arachman
audience: admin
description: Informazioni su come preparare e gestire la rete Microsoft teams. Le informazioni includono requisiti di rete, requisiti di larghezza di banda e considerazioni aggiuntive.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0d331a063feacbaea5cb510c316d2b27d982eb03
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41834636"
---
# <a name="prepare-your-organizations-network-for-microsoft-teams"></a>Preparare la rete dell'organizzazione per Microsoft Teams


Teams combina tre forme di traffico:

-   Traffico dati tra l'ambiente Office 365 online e il client Teams (segnalazione, presenza, chat, caricamento e download di file, sincronizzazione di OneNote).

-   Traffico di comunicazioni in tempo reale peer-to-peer (audio, video, condivisione desktop).

-   Traffico delle comunicazioni in tempo reale per i servizi di conferenza (audio, video, condivisione desktop).

Questo ha un impatto sulla rete su due livelli: il traffico scorrerà tra i client di Microsoft teams direttamente per gli scenari peer-to-peer e il traffico scorrerà tra l'ambiente di Office 365 e i client di Microsoft teams per gli scenari di riunione. Per garantire un flusso di traffico ottimale, il traffico deve essere consentita per il flusso sia tra i segmenti di rete interni, ad esempio tra i siti della WAN, sia tra i siti di rete e Office 365. Non aprire le porte corrette o bloccare attivamente porte specifiche comporterà un'esperienza degradata.


Per ottenere un'esperienza ottimale con i contenuti multimediali in tempo reale in Microsoft teams, la rete deve soddisfare i requisiti di rete per Office 365. Per altre informazioni, Vedi [qualità multimediale e prestazioni della connettività di rete per Skype for business online](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance).

Per i due segmenti di rete che definiscono (client per Microsoft Edge e Customer Edge in Microsoft Edge), prendere in considerazione i seguenti suggerimenti.


|Valore  |Client in Microsoft Edge  |Customer Edge to Microsoft Edge  |
|:--- |:--- |:--- |
|**Latenza (solo andata)**\*  |< 50ms          |< 30ms         |
|**Latenza (RTT o periodo di andata e ritorno)**\* |< 100ms   |< 60ms |
|**Perdita di pacchetti burst**    |<10% durante l'intervallo di 200ms         |<1% durante l'intervallo di 200ms         |
|**Perdita di pacchetti**     |<1% durante qualsiasi intervallo di 15s          |<0,1% durante qualsiasi intervallo di 15s         |
|**Jitter tra i pacchetti di arrivo**    |<30ms durante qualsiasi intervallo di 15s         |<15ms durante qualsiasi intervallo di 15s         |
|**Riordino dei pacchetti**    |<pacchetti fuori ordine di 0,05%         |<pacchetti fuori ordine di 0,01%         |

\*Le destinazioni metriche per la latenza presuppongono che il sito o i siti aziendali e i bordi Microsoft si trovino nello stesso continente.

La connessione del sito aziendale a Microsoft Network Edge include il primo accesso alla rete hop, che può essere Wi-Fi o un'altra tecnologia wireless.

Le destinazioni delle prestazioni di rete presuppongono una corretta pianificazione della larghezza di banda e/o [QoS](QoS-in-Teams.md). In altre parole, i requisiti si applicano direttamente al traffico multimediale in tempo reale dei team quando la connessione di rete è sotto un carico di picco.

Per altre informazioni sulla preparazione della rete per i team, vedere [Network Planner](https://docs.microsoft.com/microsoftteams/network-planner).


## <a name="bandwidth-requirements"></a>Requisiti di larghezza di banda
Microsoft teams offre la migliore esperienza di condivisione di audio, video e contenuti indipendentemente dalle condizioni della rete. Con i codec variabili, i contenuti multimediali possono essere negoziati in ambienti con larghezza di banda limitata con un impatto minimo. Ma se la larghezza di banda non è un problema, le esperienze possono essere ottimizzate per la qualità, ad esempio fino a risoluzione video 1080p, fino a 30fps per video e 15fps per il contenuto e audio ad alta fedeltà.

[!INCLUDE [Bandwidth requirements](includes/bandwidth-requirements.md)]


<!--
The content you will find below can be used as supplemental background information; however, it is recommended that customers use [Network Planner](https://aka.ms/bwcalc) to track their needs.

> [!IMPORTANT]
>If the required bandwidth is not available, the media stack inside Teams will degrade the quality of the audio/video session to accommodate for that lower amount of available bandwidth, impacting the quality of the call/meeting. The Teams client will attempt to prioritize the quality of audio over the quality of video. It is therefore extremely important to have the expected bandwidth available.


|Activity  |Download Bandwidth  |Upload Bandwidth  |Traffic Flow |
|---------|---------|---------|---------|
|**Peer to peer Audio Call**     |0.1 Mb         |0.1Mb         |Client <> Client         |
|**Peer to peer Video Call (full screen)**     |4 Mb         |4Mb         |Client <> Client          |
|**Peer to peer Desktop Sharing (1920*1080 resolution)**     |4 Mb         |4 Mb         |Client <> Client          |
|**2 Participant Meeting**     |4 Mb         |4 Mb         |Client <> Office 365         |
|**3 participant meeting**     |8 Mb         |6.5 Mb         |Client <> Office 365           |
|**4 participant meeting**     |5.5 Mb         |4 Mb         |Client <> Office 365           |
|**5 participant+ meeting**     |6 Mb         |1.5 Mb         |Client <> Office 365           |
-->

<a name="additional-network-considerations"></a>Considerazioni di rete aggiuntive
---------------

#### <a name="external-name-resolution"></a>Risoluzione dei nomi esterni

Assicurarsi che tutti i computer client che eseguono teams client possano risolvere le query DNS esterne per individuare i servizi forniti da Office 365 e che i firewall non impediscano l'accesso. Per informazioni sulla configurazione delle porte del firewall, vedere [URL e intervalli di indirizzi IP di Office 365](office-365-urls-ip-address-ranges.md).

#### <a name="nat-pool-size"></a>Dimensioni pool NAT

Quando più utenti/dispositivi accedono a Office 365 tramite NAT (Network Address Translation) o PAT (Port Address Translation), è necessario assicurarsi che i dispositivi nascosti dietro ogni indirizzo IP instradabile pubblicamente non superino il numero supportato.

Per ovviare a questo rischio, assicurati che siano assegnati indirizzi IP pubblici adeguati ai pool NAT per evitare l'esaurimento della porta. L'esaurimento della porta causerà gli utenti e i dispositivi finali interni per affrontare i problemi quando si connette ai servizi di Office 365. Per altre informazioni, vedere [supporto NAT con Office 365](https://support.office.com/article/NAT-support-with-Office-365-170e96ea-d65d-4e51-acac-1de56abe39b9).

#### <a name="intrusion-detection-and-prevention-guidance"></a>**Istruzioni per il rilevamento delle intrusioni e la prevenzione**

Se l'ambiente ha un sistema di rilevamento delle intrusioni e/o sistemi di prevenzione (IDS/IPS) distribuiti per un ulteriore livello di sicurezza per le connessioni in uscita, verificare che il traffico con gli URL di Office 365 sia in whitelist.

<a name="network-health-determination"></a>Determinazione dell'integrità della rete
-----------------

Quando si pianifica l'implementazione di Microsoft teams all'interno della rete, è necessario assicurarsi di avere la larghezza di banda necessaria, si ha accesso a tutti gli indirizzi IP necessari, alle porte corrette aperte e si soddisfano i requisiti di prestazioni per i supporti in tempo reale .

Se si sa che non si soddisfano questi criteri, gli utenti finali non otterranno un'esperienza ottimale da parte di Teams a causa della cattiva qualità durante le chiamate e le riunioni.

Se non si soddisfano questi criteri, è il momento di prendere in considerazione la possibilità di sospendere il progetto per verificare che i criteri vengano soddisfatti prima di continuare.


|  |  |  |
|---------|---------|---------|
|![Icona che rappresenta un punto decisionale](media/Prepare_your_organizations_network_for_Microsoft_Teams_image3.png)    |Punto decisionale         |Hai valutato le funzionalità di rete per il supporto di elementi multimediali in tempo reale?<br></br>Se la rete non è stata valutata correttamente o se si è certi che non supporta il supporto in tempo reale, si disabilitano le funzionalità di condivisione di video e schermo per ridurre l'impatto della rete e le esperienze dei team poveri?         |
|![Icona che rappresenta i passaggi successivi](media/Prepare_your_organizations_network_for_Microsoft_Teams_image4.png)     |Operazioni successive         |Qualità della rete sconosciuta: eseguire una valutazione della conformità della rete per determinare se la rete è pronta per il supporto in tempo reale.<br></br>Qualità della rete scadente: eseguire i passaggi per la risoluzione dei problemi di rete per garantire un ambiente appropriato per i media in tempo reale di alta qualità.<br></br>Rete soddisfacente: verificare che tutti gli indirizzi IP e le porte siano correttamente accessibili.           |

## <a name="related-topics"></a>Argomenti correlati

[Video: pianificazione della rete](https://aka.ms/teams-networking)
