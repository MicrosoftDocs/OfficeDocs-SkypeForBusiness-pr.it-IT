---
title: Microsoft Teams Rooms versione dell'app
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
description: Informazioni sul supporto del ciclo di vita Microsoft Teams Rooms, tra cui la struttura del supporto dinamico e le relative fasi.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d6ac865a59f2342b97ddb8cb0ae5807427c10b85
ms.sourcegitcommit: 50ec59b454e751d952cde9fd13c8017529d0e1d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2021
ms.locfileid: "52469678"
---
# <a name="microsoft-teams-rooms-app-version-support"></a>Microsoft Teams Rooms versione dell'app
 
L Microsoft Teams Rooms app riceve gli aggiornamenti alcune volte all'anno. Ogni aggiornamento è supportato per dodici (12) mesi dalla data di rilascio della disponibilità generale (GA). Il supporto tecnico viene fornito per tutti i dodici (12) mesi. Tuttavia, la struttura del supporto è dinamica, con due fasi distinte che dipendono dalla disponibilità della versione più recente:

- **Fase manutenzione e aggiornamenti critici:** quando si esegue l'ultima versione dell'app Microsoft Teams Rooms, si ricevono regolarmente aggiornamenti che contengono gli aggiornamenti di sicurezza *e manutenzione.*

- Fase Solo aggiornamenti della **sicurezza:** quando viene rilasciata una nuova versione dell'app Microsoft Teams Rooms, le versioni precedenti dell'app hanno un livello di supporto ridotto con gli aggiornamenti della sicurezza solo per il resto del ciclo di vita di dodici (12) mesi. 

> [!NOTE]
> La versione più recente è sempre in fase di manutenzione e aggiornamenti critici. Quando si verifica un difetto di codice che garantisce un aggiornamento critico, è necessario che sia installata anche la versione più recente per ricevere una correzione. Tutte le altre versioni supportate saranno idonee solo per ricevere gli aggiornamenti della sicurezza.

Tutto il supporto termina dopo che il ciclo di vita di dodici (12) mesi per una versione è scaduto o se da allora sono stati rilasciati più di due aggiornamenti. I clienti devono quindi eseguire l'aggiornamento a una versione supportata.

Tutti i rilasci sono elencati nelle [note Microsoft Teams Rooms rilascio.](rooms-release-note.md)

## <a name="windows-10-release-support"></a>Windows 10 di rilascio

Microsoft Teams Rooms richiede le Windows 10 IoT Enterprise o Windows 10 Enterprise SKU nelle opzioni di manutenzione Semi-Annual Channel. Le altre Windows 10 non sono supportate:

- Windows 10 Enterprise Edizioni long-term Servicing Branch (LTSB) /Long Term Servicing Channel (LTSC)
- Windows 10 Internet of Things (IoT) Enterprise edizioni LTSB/LTSC
- qualsiasi altra edizione di Windows, ad esempio Windows 10 Pro o Home edition

I Windows 10 delle funzionalità non vengono offerti immediatamente nei Microsoft Teams Rooms mobili. Ritardo intenzionale fino a sei mesi dopo la data di disponibilità generale pubblicata nella Windows 10 [informazioni sul rilascio.](/windows/release-information/) Il tempo di ritardo viene usato per convalidare la Windows 10 di rilascio per l'app Microsoft Teams Rooms, l'hardware del dispositivo e le periferiche video audio certificate. La convalida inizia e continua durante lo sviluppo attivo di ogni rilascio principale di Windows 10. È necessario un tempo aggiuntivo per verificare che tutti i produttori di dispositivi hanno creato immagini aggiornate per i propri dispositivi e per Microsoft Teams certificare e testare tali immagini. Durante il periodo di convalida, l'app room Microsoft Teams l'app Windows criteri di gruppo [Di aggiornamento per](/windows/deployment/update/waas-manage-updates-wufb) le aziende per ritardare Windows 10 aggiornamenti delle funzionalità. Dopo aver trovato e risolto eventuali problemi di compatibilità, il blocco viene revocato tramite l'aggiornamento dei criteri di gruppo tramite una nuova versione dell'app in Windows Store. I dispositivi che eseguono l Microsoft Teams Rooms app vengono aggiornati automaticamente a un rilascio Windows 10 durante il riavvio della manutenzione notturna. Una versione MSI viene resa disponibile per i clienti che desiderano gestire manualmente gli aggiornamenti.  

> [!IMPORTANT]
> Durante il periodo di convalida, Microsoft Teams Rooms dispositivi non **devono** essere aggiornati alla versione successiva di Windows 10 con qualsiasi mezzo. Ciò include l'override dei criteri di gruppo o l'System Center o altri servizi di gestione dei dispositivi di terze parti. Uno di questi potrebbe causare problemi per l'app Microsoft Teams Room o potrebbe lasciare i dispositivi inutilizzabili.  

La tabella seguente mostra le versioni consigliate e supportate Windows 10 verificate per supportare Microsoft Teams Rooms. Tutte le date sono elencate nel formato ISO 8601: AAAA-MM-GG.

|Versione  |Data disponibilità   |Microsoft Teams Rooms supporto tecnico   |Microsoft Teams Rooms Versione minima dell'applicazione | Build del sistema operativo consigliata  |
|:---  |:---       |:---                                  |:---     |:---     |
| 20H2 |2020-10-20 |Supportato, <br/>Scelta consigliata|4.8.31.0 |19042.631 |
| 2004 |2020-05-27 |Ignorato, <br/> Non consigliato &#x2780;|&#x2014; |&#x2014; |
| 1909 |2019-11-12 |Supportato |4.5.33.0 |18363.418  |
| 1903 |2019-05-21 |Non supportato  |&#x2014; |&#x2014; |
| 1809 |2019-03-28 |Non supportato, <br/>Problemi noti di compatibilità &#x2781;|&#x2014; |&#x2014; |
| 1803 |2018-07-10 |Non supportato                             |&#x2014;  |&#x2014; |
| 1709 |2018-01-18 |Non supportato                         |&#x2014; |&#x2014; |
| 1703 |2017-07-11 |Non supportato                         |&#x2014; |&#x2014; |

&#x2780; Windows 10 la versione 2004 non è consigliata a causa di problemi di compatibilità riscontrati con l'Microsoft Teams Rooms applicazione. Questo problema specifico causa l'Microsoft Teams Rooms'avvio dell'applicazione dopo il riavvio notturno. 

&#x2781; Windows 10 la versione 1809 non è consigliata a causa di problemi di compatibilità riscontrati con l'Microsoft Teams Rooms applicazioni. Questo problema specifico causa l'Microsoft Teams Rooms'avvio dell'applicazione dopo il riavvio notturno. Questo problema è stato risolto nella Windows 10 1903.  

Quando si usa una versione supportata di Windows 10, si otterrà sempre gli aggiornamenti più recenti delle applicazioni per l'app Microsoft Teams Rooms.  

> [!IMPORTANT]
> L Windows 10 20H2 non è ancora disponibile per i dispositivi Teams Rooms seguenti a causa di problemi di compatibilità. Gli OEM dei dispositivi stanno lavorando per risolvere questi problemi il prima possibile. Windows 10 20H2 non verrà offerto su questi dispositivi. Non aggiornare manualmente questi dispositivi a 20H2 eseguendo l'override degli oggetti Criteri di gruppo (GPO) o della gestione di dispositivi mobili (MDM). 
> 
> I dispositivi con problemi di compatiablità sono:
> 
> - HP Elite Slice
> - HP Elite Slice G2 MS SRS Audio Ready
> - HP Elite Slice MS SRS Partner Ready
> - HP Elite Slice G2 con MS MTR
> - Crestron UC-Engine (la versione/data del BIOS contiene "KYSKLI" - che indica un BIOS Skull Canyon) 

## <a name="related-topics"></a>Argomenti correlati

[Microsoft Teams Rooms guida](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Microsoft Teams Rooms sulla versione](rooms-release-note.md)

[Piano per Microsoft Teams Rooms](rooms-plan.md)
