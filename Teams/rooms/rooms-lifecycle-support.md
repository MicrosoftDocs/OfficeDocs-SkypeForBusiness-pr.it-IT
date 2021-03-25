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
description: Informazioni sul supporto del ciclo di vita per Microsoft Teams Rooms, tra cui la struttura del supporto dinamico e le relative fasi.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e22bf9759920a5b4233fab9a6f6169f3a1153f0d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117444"
---
# <a name="microsoft-teams-rooms-app-version-support"></a>Supporto per la versione dell'app Microsoft Teams Rooms
 
L'app Microsoft Teams Rooms riceve gli aggiornamenti alcune volte all'anno. Ogni aggiornamento supportato per dodici (12) mesi dalla data di rilascio della disponibilità generale (GA). Il supporto tecnico viene fornito per tutti i dodici (12) mesi. Tuttavia, la struttura del supporto è dinamica, con due fasi distinte che dipendono dalla disponibilità della versione più recente:

- **Fase manutenzione e aggiornamenti critici** \- Quando si esegue l'ultima versione dell'app Microsoft Teams Rooms, si ricevono regolarmente aggiornamenti che contengono aggiornamenti per la sicurezza *e la* manutenzione.

- **Fase Solo aggiornamenti della sicurezza** \- Quando viene rilasciata una nuova versione dell'app Microsoft Teams Rooms,  le versioni precedenti dell'app hanno un livello di supporto ridotto con gli aggiornamenti della sicurezza solo per il resto del ciclo di vita di dodici (12) mesi.

> [!NOTE]
> La versione più recente è sempre in fase di manutenzione e aggiornamenti critici. Quando si verifica un difetto di codice che garantisce un aggiornamento critico, è necessario che sia installata anche la versione più recente per ricevere una correzione. Tutte le altre versioni supportate saranno idonee solo per ricevere gli aggiornamenti della sicurezza.

Tutto il supporto termina dopo che il ciclo di vita di dodici (12) mesi per una versione è scaduto o se da allora sono stati rilasciati più di due aggiornamenti. I clienti devono quindi eseguire l'aggiornamento a una versione supportata.

Tutte le versioni sono elencate nelle [note sulla versione di Microsoft Teams Rooms.](rooms-release-note.md)

## <a name="windows-10-release-support"></a>Supporto per il rilascio di Windows 10

Microsoft Teams Rooms richiede le SKU Windows 10 IoT Enterprise o Windows 10 Enterprise in Semi-Annual di manutenzione del Canale. Queste altre edizioni di Windows 10 non sono supportate:

- Windows 10 Enterprise Long-Term Servicing Branch (LTSB) / edizioni di Long Term Servicing Channel (LTSC)
- Windows 10 Internet of Things (IoT) Enterprise LTSB / edizioni LTSC
- qualsiasi altra edizione di Windows, ad esempio Windows 10 Pro o Home Edition

Un aggiornamento delle funzionalità di Windows 10 non viene offerto o aggiornato immediatamente nei dispositivi Microsoft Teams Rooms. Ritardo intenzionale fino a sei mesi dopo la data di disponibilità generale pubblicata nella pagina delle informazioni sul rilascio [di Windows 10.](/windows/release-information/) Il tempo di ritardo viene usato per convalidare la compatibilità delle versioni di Windows 10 per l'applicazione Microsoft Teams Rooms, l'hardware del dispositivo e le periferiche video audio certificate. La convalida inizia e continua durante lo sviluppo attivo di ogni versione principale di Windows 10. È necessario un tempo aggiuntivo per verificare che tutti i produttori di dispositivi abbia creato immagini aggiornate per i propri dispositivi e che Microsoft Teams certififi e test tali immagini. Durante il periodo di convalida, l'app Microsoft Teams Room usa i criteri di gruppo di  [Windows Update for Business](/windows/deployment/update/waas-manage-updates-wufb) per ritardare gli aggiornamenti delle funzionalità di Windows 10. Dopo aver trovato e risolto eventuali problemi di compatibilità, il blocco viene revocato tramite l'aggiornamento dei criteri di gruppo tramite una nuova versione dell'app in Windows Store. I dispositivi che eseguono l'app Microsoft Teams Rooms vengono aggiornati automaticamente a un rilascio appropriato di Windows 10 durante il riavvio della manutenzione notturna. Una versione MSI viene resa disponibile per i clienti che desiderano gestire manualmente gli aggiornamenti.  

> [!IMPORTANT]
> Durante il periodo di convalida,  i dispositivi Microsoft Teams Rooms non devono essere aggiornati alla prossima versione di Windows 10 con alcun mezzo. Ciò include l'override dei criteri di gruppo o l'uso di System Center o di altri servizi di gestione dei dispositivi di terze parti. Uno di questi problemi può causare problemi per l'applicazione Microsoft Teams Room o potrebbe lasciare i dispositivi inutilizzabili.  

La tabella seguente mostra le versioni consigliate e supportate di Windows 10 verificate per supportare Microsoft Teams Rooms. Tutte le date sono elencate nel formato ISO 8601: AAAA-MM-GG.

|Versione  |Data disponibilità   |Stato del supporto di Microsoft Teams Rooms   |Versione minima dell'applicazione Microsoft Teams Rooms | Build del sistema operativo consigliata  |
|:---  |:---       |:---                                  |:---     |:---     |
| 20H2 |2020-10-20 |In fase di convalida, <br/>Non ancora supportato|&#x2014; |19042.572 |
| 2004 |2020-05-27 |Ignorato, <br/> Non consigliato|&#x2014; |19041.264 |
| 1909 |2019-11-12 |Supportato, <br/>Scelta consigliata |4.5.33.0 |18363.418  |
| 1903 |2019-05-21 |Supportato  |4.2.4.0 |18362.356 |
| 1809 |2019-03-28 |Non supportato, <br/>Problemi noti di compatibilità &#x2780;|&#x2014; |&#x2014; |
| 1803 |2018-07-10 |Non supportato                             |&#x2014;  |&#x2014; |
| 1709 |2018-01-18 |Non supportato                         |&#x2014; |&#x2014; |
| 1703 |2017-07-11 |Non supportato                         |&#x2014; |&#x2014; |

&#x2780; windows 10 versione 1809 non è consigliato a causa di problemi di compatibilità riscontrati con l'applicazione Microsoft Teams Rooms. Questo problema specifico causa l'avvio dell'applicazione Microsoft Teams Rooms dopo il riavvio notturno. Questo problema è stato risolto in Windows 10 versione 1903.  

&#x2781; windows 10 versione 2004 non è consigliabile a causa di problemi di compatibilità riscontrati con l'applicazione Microsoft Teams Rooms. Questo problema specifico causa l'avvio dell'applicazione Microsoft Teams Rooms dopo il riavvio notturno. 

Quando si usa una versione supportata di Windows 10, si otterrà sempre gli aggiornamenti più recenti dell'applicazione per l'app Microsoft Teams Rooms.  

## <a name="related-topics"></a>Argomenti correlati

[Guida di Microsoft Teams Rooms](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Note sulla versione di Microsoft Teams Rooms](rooms-release-note.md)

[Piano per Microsoft Teams Rooms](rooms-plan.md)