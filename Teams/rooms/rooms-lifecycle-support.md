---
title: Supporto per la versione
ms.author: v-lanac
author: lanachin
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
description: Informazioni sul supporto del ciclo di vita per le sale di Microsoft teams, tra cui la struttura di supporto dinamico e le relative fasi.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 17e1dcd3c473b31754ac29d98db04747798d581f
ms.sourcegitcommit: 3a577c07b4f399c81d8650a2bba8cfc00b695b49
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/21/2020
ms.locfileid: "48650919"
---
# <a name="microsoft-teams-rooms-app-version-support"></a>Supporto per la versione dell'app Microsoft teams rooms
 
L'app Microsoft teams Rooms ottiene gli aggiornamenti alcune volte all'anno. Ogni aggiornamento supportato per dodici (12) mesi dalla data di rilascio per la disponibilità generale (GA). Il supporto tecnico è disponibile per gli interi dodici (12) mesi. La struttura di supporto è tuttavia dinamica, con due fasi distinte che dipendono dalla disponibilità della versione più recente:

- Fase di manutenzione **e aggiornamenti critici** \- Quando si esegue la versione più recente dell'app Microsoft teams rooms, vengono visualizzati aggiornamenti periodici che contengono aggiornamenti della *sicurezza e della manutenzione* .

- **Solo fase** \- aggiornamenti della sicurezza Quando viene rilasciata una nuova versione dell'app Microsoft teams rooms, le versioni precedenti dell'app hanno un livello di supporto ridotto con *gli aggiornamenti della sicurezza solo* per il resto del ciclo di vita dei dodici (12) mesi.

> [!NOTE]
> La versione più recente è sempre nella fase di manutenzione e aggiornamenti critici. Quando si verifica un errore di codice che garantisce un aggiornamento critico, è necessario che sia installata anche la versione più recente per ricevere una correzione. Tutte le altre versioni supportate saranno idonee solo per ricevere gli aggiornamenti della sicurezza.

Tutti i supporti terminano dopo la scadenza del ciclo di vita di dodici (12) mesi per una versione o se da allora sono stati rilasciati più di due aggiornamenti. I clienti devono quindi eseguire l'aggiornamento a una versione supportata.

Tutte le versioni sono elencate nelle [Note sulla versione di Microsoft teams Rooms](rooms-release-note.md).

## <a name="windows-10-release-support"></a>Supporto per Windows 10 Release

Le sale di Microsoft teams richiedono gli SKU Enterprise di Windows 10 o Windows 10 Enterprise in Semi-Annual opzioni di manutenzione dei canali. Queste altre edizioni di Windows 10 non sono supportate:

- Windows 10 Enterprise Branch Servicing a lungo termine (LTSB)/edizioni LTSC (Long Term Servicing Channel)
- Windows 10 Internet of Things (molto) Enterprise LTSB/LTSC Editions
- qualsiasi altra edizione di Windows, ad esempio Windows 10 Pro o Home Edition

Un aggiornamento delle funzionalità di Windows 10 non viene offerto o aggiornato nei dispositivi Microsoft teams Rooms immediatamente. Un ritardo intenzionale fino a sei mesi dopo la data di disponibilità generale pubblicata nella pagina delle [informazioni sulla versione di Windows 10](https://docs.microsoft.com/windows/release-information/) . Il tempo di ritardo viene usato per convalidare la compatibilità delle versioni di Windows 10 per l'applicazione sale di Microsoft teams, l'hardware del dispositivo e le periferiche audio video certificate. La convalida inizia e continua durante lo sviluppo attivo di ogni versione principale di Windows 10. È necessario un tempo aggiuntivo per verificare che tutti i produttori di dispositivi abbiano creato immagini aggiornate per i propri dispositivi e che Microsoft teams sia in grado di certificare e testare tali immagini. Durante il periodo di convalida, l'app Microsoft teams room usa i  [criteri di gruppo di Windows Update for business](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) per ritardare gli aggiornamenti delle funzionalità di Windows 10. Dopo che i problemi di compatibilità vengono trovati e risolti, il blocco viene revocato tramite l'aggiornamento dei criteri di gruppo tramite una nuova versione dell'app in Windows Store. I dispositivi che eseguono l'app Microsoft teams Rooms vengono aggiornati automaticamente in una versione di Windows 10 appropriata durante il riavvio della manutenzione notturna. Una versione MSI viene resa disponibile per i clienti che desiderano gestire manualmente gli aggiornamenti.  

> [!IMPORTANT]
> Durante il periodo di convalida, i dispositivi Microsoft teams Rooms **non** devono essere aggiornati alla versione successiva di Windows 10 con qualsiasi mezzo. Ciò include l'override dei criteri di gruppo in posizione o l'uso di System Center o di altri servizi di gestione dei dispositivi di terze parti. Qualsiasi di queste operazioni può causare problemi per l'applicazione della sala Microsoft teams o può abbandonare i dispositivi inutilizzabili.  

La tabella seguente mostra le versioni consigliate e supportate di Windows 10 verificate per supportare le sale di Microsoft teams. Tutte le date sono elencate nel formato ISO 8601: AAAA-MM-DD.

|Versione  |Data di disponibilità   |Stato supporto di Microsoft teams rooms   |Versione minima dell'applicazione di Microsoft teams rooms | Build del sistema operativo consigliata  |
|:---  |:---       |:---                                  |:---     |:---     |
| 20H2 |2020-10-20 |In convalida <br/>Non ancora supportata|&#x2014; |19042,572 |
| 2004 |2020-05-27 |Ignorato <br/> Non raccomandato|&#x2014; |19041,264 |
| 1909 |2019-11-12 |Supportati <br/>Consigliato |4.5.33.0 |18363,418  |
| 1903 |2019-05-21 |Supportati  |4.2.4.0 |18362,356 |
| 1809 |2019-03-28 |Non supportato <br/>Problemi di compatibilità noti &#x2780;|&#x2014; |&#x2014; |
| 1803 |2018-07-10 |Non supportato                             |&#x2014;  |&#x2014; |
| 1709 |2018-01-18 |Non supportato                         |&#x2014; |&#x2014; |
| 1703 |2017-07-11 |Non supportato                         |&#x2014; |&#x2014; |

&#x2780; Windows 10 versione 1809 non è consigliabile a causa di problemi di compatibilità trovati con l'applicazione Microsoft teams rooms. Questo problema specifico fa in modo che l'applicazione sale di Microsoft teams non venga avviata dopo il riavvio notturno. Questo problema è stato risolto in Windows 10 versione 1903.  

&#x2781; Windows 10 versione 2004 non è consigliabile a causa di problemi di compatibilità trovati con l'applicazione Microsoft teams rooms. Questo problema specifico fa in modo che l'applicazione sale di Microsoft teams non venga avviata dopo il riavvio notturno. 

Quando usi una versione supportata di Windows 10, otterrai sempre gli aggiornamenti delle applicazioni più recenti per l'app Microsoft teams rooms.  

## <a name="related-topics"></a>Argomenti correlati

[Guida di Microsoft teams rooms](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Note sulla versione di Microsoft teams rooms](rooms-release-note.md)

[Piano per Microsoft Teams Rooms](rooms-plan.md)
