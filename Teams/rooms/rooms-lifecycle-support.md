---
title: Supporto delle versioni
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
localization_priority: Normal
description: Informazioni sul supporto del ciclo di vita per le sale di Microsoft Teams, inclusa la struttura di supporto dinamico e le relative fasi.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 584f4661a39d21f916b2097c242f71b996c568e6
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662451"
---
# <a name="microsoft-teams-rooms-app-version-support"></a>Supporto della versione dell'app Microsoft Teams Rooms
 
L'app Sale di Microsoft Teams riceve gli aggiornamenti alcune volte all'anno. Ogni aggiornamento è supportato per dodici (12) mesi dalla data di rilascio della disponibilità generale. Il supporto tecnico viene fornito per tutti e dodici (12) mesi. Tuttavia, la struttura di supporto è dinamica, con due fasi distinte che dipendono dalla disponibilità dell'ultima versione:

- **Fase di manutenzione e aggiornamenti critici** \- Quando si esegue l'ultima versione dell'app Sale di Microsoft Teams, si ricevono aggiornamenti regolari che contengono gli aggiornamenti per la sicurezza *e la* manutenzione.

- **Fase Solo aggiornamenti della sicurezza** \- Quando viene rilasciata una nuova versione dell'app Sale di Microsoft  Teams, le versioni precedenti dell'app hanno un livello di supporto ridotto con gli aggiornamenti della sicurezza solo per il resto del ciclo di vita di dodici (12) mesi.

> [!NOTE]
> La versione più recente è sempre nella fase di manutenzione e aggiornamento critico. Quando si verifica un difetto di codice che garantisce un aggiornamento critico, per ricevere una correzione è necessario avere installato anche la versione più recente. Tutte le altre versioni supportate saranno idonee solo per ricevere gli aggiornamenti della sicurezza.

Tutto il supporto termina dopo la scadenza di dodici (12) mesi del ciclo di vita di una versione o se da quel momento sono stati rilasciati più di due aggiornamenti. I clienti devono quindi eseguire l'aggiornamento a una versione supportata.

Tutti i rilasci sono elencati nelle [note sulla versione di Microsoft Teams Rooms.](rooms-release-note.md)

## <a name="windows-10-release-support"></a>Supporto per i rilasci di Windows 10

Microsoft Teams Rooms richiede le SKU Windows 10 IoT Enterprise o Windows 10 Enterprise nelle Semi-Annual di manutenzione dei canali. Queste altre edizioni di Windows 10 non sono supportate:

- Edizioni Windows 10 Enterprise Long-Term Servicing Branch (LTSB) /Long Term Servicing Channel (LTSC)
- Edizioni Internet of Things (IoT) Enterprise LTSB/LTSC di Windows 10
- qualsiasi altra edizione di Windows, ad esempio Windows 10 Pro o Home

Un aggiornamento delle funzionalità di Windows 10 non viene offerto né aggiornato sui dispositivi Microsoft Teams Room immediatamente. Un ritardo intenzionale fino a sei mesi dopo la data di disponibilità generale pubblicata nella pagina delle informazioni sul rilascio di [Windows 10.](https://docs.microsoft.com/windows/release-information/) Il tempo di ritardo viene usato per convalidare la compatibilità dei rilasci di Windows 10 per l'applicazione Sale di Microsoft Teams, l'hardware del dispositivo e le periferiche audio video certificate. La convalida inizia e continua durante lo sviluppo attivo di ogni versione principale di Windows 10. È necessario altro tempo per verificare che tutti i produttori di dispositivi hanno creato immagini aggiornate per i propri dispositivi e per fare in modo che Microsoft Teams certififi e testa tali immagini. Durante il periodo di convalida, l'app Microsoft Teams Room usa i criteri di gruppo di  [Windows Update for Business](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) per posticipare gli aggiornamenti delle funzionalità di Windows 10. Una volta rilevati e risolti eventuali problemi di compatibilità, il blocco viene revocato tramite l'aggiornamento dei criteri di gruppo tramite una nuova versione dell'app in Windows Store. I dispositivi che eseguono l'app Sale di Microsoft Teams vengono aggiornati automaticamente a un rilascio di Windows 10 appropriato durante il riavvio di manutenzione notturna. Viene resa disponibile una versione MSI per i clienti che vogliono gestire manualmente gli aggiornamenti.  

> [!IMPORTANT]
> Durante il periodo di convalida,  i dispositivi Microsoft Teams Room non devono essere aggiornati alla versione successiva di Windows 10 con alcun mezzo. Ciò include l'override dei criteri di gruppo presenti oppure l'uso di System Center o di altri servizi di gestione di dispositivi di terze parti. Questi problemi possono causare problemi all'applicazione Microsoft Teams Room o potrebbero lasciare inutilizzabili i dispositivi.  

La tabella seguente mostra le versioni consigliate e supportate di Windows 10 verificate per il supporto delle sale di Microsoft Teams. Tutte le date sono elencate nel formato ISO 8601: AAAA-MM-GG.

|Versione  |Data disponibilità   |Stato di supporto di Microsoft Teams Rooms   |Versione minima dell'applicazione Microsoft Teams Rooms | Build del sistema operativo consigliata  |
|:---  |:---       |:---                                  |:---     |:---     |
| 20H2 |2020-10-20 |In Convalida <br/>Non ancora supportato|&#x2014; |19042.572 |
| 2004 |2020-05-27 |Ignorato, <br/> Non consigliato|&#x2014; |19041.264 |
| 1909 |2019-11-12 |Supportata, <br/>Consigliati |4.5.33.0 |18363.418  |
| 1903 |2019-05-21 |Supportata  |4.2.4.0 |18362.356 |
| 1809 |2019-03-28 |Non supportato, <br/>Problemi di compatibilità &#x2780;|&#x2014; |&#x2014; |
| 1803 |2018-07-10 |Non supportato                             |&#x2014;  |&#x2014; |
| 1709 |2018-01-18 |Non supportato                         |&#x2014; |&#x2014; |
| 1703 |2017-07-11 |Non supportato                         |&#x2014; |&#x2014; |

&#x2780; windows 10 versione 1809 non è consigliabile a causa di problemi di compatibilità riscontrati con l'applicazione Sale di Microsoft Teams. Questo problema specifico causa l'avvio dell'applicazione Sale di Microsoft Teams dopo il riavvio sereno. Questo problema è stato risolto in Windows 10 versione 1903.  

&#x2781; windows 10 versione 2004 non è consigliabile a causa di problemi di compatibilità riscontrati con l'applicazione Sale di Microsoft Teams. Questo problema specifico causa l'avvio dell'applicazione Sale di Microsoft Teams dopo il riavvio sereno. 

Quando si usa una versione supportata di Windows 10, si ottengono sempre gli ultimi aggiornamenti dell'applicazione per l'app Sale di Microsoft Teams.  

## <a name="related-topics"></a>Argomenti correlati

[Guida di Microsoft Teams Rooms](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Note sulla versione di Microsoft Teams Rooms](rooms-release-note.md)

[Piano per Microsoft Teams Rooms](rooms-plan.md)
