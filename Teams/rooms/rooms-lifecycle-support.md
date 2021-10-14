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
ms.localizationpriority: medium
description: Informazioni sul supporto del ciclo di vita Microsoft Teams Rooms, tra cui la struttura del supporto dinamico e le relative fasi.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7e7a82d7643a925d5c997c9d6fe5661a421d47ab
ms.sourcegitcommit: 31da77589ac82c43a89a9c53f2a2de5ab52f93c0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/14/2021
ms.locfileid: "60356424"
---
# <a name="microsoft-teams-rooms-app-version-support"></a>Microsoft Teams Rooms versione dell'app
 
L Microsoft Teams Rooms app riceve gli aggiornamenti trimestrali tramite Windows Store. È possibile eseguire un aggiornamento fuori banda per risolvere i problemi urgenti. Microsoft Teams L'app Room usa un ciclo di vita del prodotto sempreverde e solo la versione corrente e l'ultima dell'app sono supportate in un determinato momento. L Microsoft Teams app Room include una versione specifica dell'app desktop Teams che viene modificata per l'uso della sala. L Teams app desktop viene aggiornata ogni due settimane. Altre informazioni sul processo [Teams di aggiornamento.](../teams-client-update.md) Questo significa che Teams Rooms versione corrente-1 dell'app può contenere fino Teams sei aggiornamenti dell'app desktop, quindi è consigliabile mantenere sempre aggiornata l'applicazione room di Teams alla versione più recente dell'app Teams Rooms. 

La struttura di supporto per Teams Rooms è dinamica e dipende dalla disponibilità della versione più recente. Quando si verifica un difetto di codice in una versione dell'applicazione che non è la più recente, è necessario installare la versione più recente per ricevere una correzione.

Tutti i rilasci sono elencati nelle [note Microsoft Teams Rooms rilascio.](rooms-release-note.md)

> [!IMPORTANT]
> Quando si installa un nuovo dispositivo fornito con una versione precedente dell'applicazione [](manual-update.md) room di Teams, è consigliabile aggiornare manualmente l'applicazione dopo aver impostato l'account, prima di scaricare gli Windows aggiornamenti. In questo modo la versione del sistema operativo correbt e gli aggiornamenti vengono installati nel dispositivo.  

## <a name="windows-10-release-support"></a>Windows 10 di rilascio

Microsoft Teams Rooms richiede le SKU Windows 10 IoT Enterprise o Windows 10 Enterprise in Semi-Annual di manutenzione del Canale. Le altre Windows 10 non sono supportate:

- Windows 10 Enterprise Edizioni long-term Servicing Branch (LTSB) /Long Term Servicing Channel (LTSC)
- Windows 10 Internet of Things (IoT) Enterprise edizioni LTSB/LTSC
- qualsiasi altra edizione di Windows, ad esempio Windows 10 Pro o Home Edition

I Windows 10 delle funzionalità non vengono offerti Microsoft Teams Rooms immediatamente. Si verifica un ritardo intenzionale fino a sei mesi o più dopo la data di disponibilità generale pubblicata nella pagina Windows 10 informazioni [sulla versione.](/windows/release-information/) Questa volta viene usata per convalidare la Windows 10 di rilascio per l'app Microsoft Teams Rooms, l'hardware del dispositivo e le periferiche video audio certificate. La convalida inizia e continua durante lo sviluppo attivo di ogni rilascio principale di Windows 10. È necessario un tempo aggiuntivo per verificare che tutti i produttori di dispositivi hanno creato immagini aggiornate per i propri dispositivi e per Microsoft Teams certificare e testare tali immagini. Durante il periodo di convalida, l Microsoft Teams app Room usa i criteri di gruppo [di Windows Update for Business](/windows/deployment/update/waas-manage-updates-wufb) per ritardare Windows 10 aggiornamenti delle funzionalità. Dopo aver trovato e risolto eventuali problemi di compatibilità, il blocco viene revocato tramite l'aggiornamento dei criteri di gruppo tramite una nuova versione dell'app in Windows Store. I dispositivi che eseguono l Microsoft Teams Rooms app vengono aggiornati automaticamente a un rilascio Windows 10 durante il riavvio della manutenzione notturna. Una versione MSI viene resa disponibile per i clienti che desiderano gestire manualmente gli aggiornamenti.  

> [!IMPORTANT]
> Durante il periodo di convalida,  Microsoft Teams Rooms dispositivi non devono essere aggiornati alla versione successiva di Windows 10 con alcun mezzo. Ciò include l'override dei criteri di gruppo o l'uso di System Center o altri servizi di gestione dei dispositivi di terze parti. Uno di questi potrebbe causare problemi per l'app Microsoft Teams Room o potrebbe lasciare i dispositivi inutilizzabili.  

La tabella seguente mostra le versioni consigliate e supportate Windows 10 verificate per supportare Microsoft Teams Rooms. Tutte le date sono elencate nel formato ISO 8601: AAAA-MM-GG.

|Versione  |Data disponibilità   |Microsoft Teams Rooms supporto tecnico   |Microsoft Teams Rooms Versione minima dell'applicazione | Build del sistema operativo consigliata  |
|:---  |:---       |:---                                  |:---     |:---     |
| 20H2 |2020-10-20 |Supportato, <br/>Consigliata|4.10.10.0 |19042.631 |
| 2004 |2020-05-27 |Ignorato, <br/> Non consigliato &#x2780;|&#x2014; |&#x2014; |
| 1909 |2019-11-12 |Supportato |4.5.33.0 |18363.418  |
| 1903 |2019-05-21 |Non supportato  |&#x2014; |&#x2014; |
| 1809 |2019-03-28 |Non supportato, <br/>Problemi noti di compatibilità &#x2781;|&#x2014; |&#x2014; |
| 1803 |2018-07-10 |Non supportato                             |&#x2014;  |&#x2014; |
| 1709 |2018-01-18 |Non supportato                         |&#x2014; |&#x2014; |
| 1703 |2017-07-11 |Non supportato                         |&#x2014; |&#x2014; |

&#x2780; Windows 10 versione 2004 non è consigliata a causa di problemi di compatibilità riscontrati con l'Microsoft Teams Rooms applicazione. Questo problema specifico causa l'Microsoft Teams Rooms'avvio dell'applicazione dopo il riavvio notturno. 

&#x2781; Windows 10 la versione 1809 non è consigliata a causa di problemi di compatibilità riscontrati con l'Microsoft Teams Rooms applicazione. Questo problema specifico causa l'Microsoft Teams Rooms'avvio dell'applicazione dopo il riavvio notturno. Questo problema è stato risolto nella Windows 10 1903.  

Quando si usa una versione supportata di Windows 10, si otterrà sempre gli aggiornamenti più recenti dell'applicazione per l Microsoft Teams Rooms app.  


## <a name="related-topics"></a>Argomenti correlati

[Guida Microsoft Teams Rooms](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Microsoft Teams Rooms sulla versione](rooms-release-note.md)

[Piano per Microsoft Teams Rooms](rooms-plan.md)
