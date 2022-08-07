---
title: Supporto della versione dell'app Microsoft Teams Rooms
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Informazioni sul supporto del ciclo di vita per Microsoft Teams Rooms, inclusa la struttura del supporto dinamico e le relative fasi.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8814ee9190ff6036345b4aa4607191d3486a369e
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2022
ms.locfileid: "67268211"
---
# <a name="microsoft-teams-rooms-app-version-support"></a>Supporto della versione dell'app Microsoft Teams Rooms
 
L'app Microsoft Teams Rooms ottiene gli aggiornamenti tramite Windows Store. L'app Microsoft Teams Room usa un ciclo di vita del prodotto sempre valido e in un determinato momento sono supportate solo la versione più recente e quella più recente dell'app. L'app Microsoft Teams Room include una versione specifica dell'app desktop Teams che viene modificata per l'uso della sala. L'app desktop Teams viene aggiornata ogni due settimane. Altre informazioni sul [processo di aggiornamento di Teams](../teams-client-update.md). Ciò significa che Teams Rooms app versione 1 corrente può avere un massimo di sei aggiornamenti delle app desktop di Teams, quindi è consigliabile mantenere l'applicazione Teams Room aggiornata all'ultima versione dell'app Teams Rooms in qualsiasi momento. 

La struttura di supporto per Teams Rooms è dinamica e dipende dalla disponibilità della versione più recente. Quando si verifica un difetto di codice in una versione dell'applicazione che non è la più recente, è necessario installare l'ultima versione per ricevere una correzione.

Tutte le versioni sono elencate nelle [note sulla versione Microsoft Teams Rooms](rooms-release-note.md).

> [!IMPORTANT]
> Quando si installa un nuovo dispositivo fornito con una versione precedente dell'applicazione sala teams, si consiglia di [aggiornare manualmente l'applicazione dopo aver impostato l'account](manual-update.md) , prima di scaricare gli aggiornamenti di Windows. In questo modo vengono installati la versione corretta del sistema operativo e gli aggiornamenti di Windows nel dispositivo.  

## <a name="windows-10-release-support"></a>supporto per i rilasci di Windows 10

Microsoft Teams Rooms richiede gli SKU Windows 10 IoT Enterprise o Windows 10 Enterprise nelle opzioni di manutenzione di Semi-Annual Channel. Queste altre edizioni Windows 10 non sono supportate:

- Windows 10 Enterprise edizioni LTSB (Long-Term Servicing Branch) /Long Term Servicing Channel (LTSC)
- Windows 10 edizioni LTSB /LTSC Enterprise Internet of Things (IoT)
- qualsiasi altra edizione di Windows, ad esempio Windows 10 Pro o Home Edition

I nuovi aggiornamenti delle funzionalità di Windows 10 non sono disponibili immediatamente nei dispositivi Microsoft Teams Rooms. Si verifica un ritardo intenzionale fino a sei mesi o più dopo la data di disponibilità generale pubblicata nella pagina [Windows 10 informazioni sulla versione](/windows/release-information/). Questa volta viene utilizzata per convalidare la compatibilità delle versioni di Windows 10 per l'app Microsoft Teams Rooms, l'hardware del dispositivo e le periferiche audio video certificate. La convalida inizia e continua durante lo sviluppo attivo di ogni versione principale di Windows 10. È necessario più tempo per verificare che tutti i produttori di dispositivi abbiano creato immagini aggiornate per i propri dispositivi e che Microsoft certifica e test tali immagini. Durante il periodo di convalida, l'app Chat room di Microsoft Teams usa i [criteri di gruppo di Windows Update for Business per](/windows/deployment/update/waas-manage-updates-wufb) posticipare Windows 10 aggiornamenti delle funzionalità. Dopo aver rilevato e risolto eventuali problemi di compatibilità, il blocco viene rimosso tramite l'aggiornamento dei criteri di gruppo tramite una nuova versione dell'app in Windows Store. I dispositivi che eseguono l'app Microsoft Teams Rooms vengono aggiornati automaticamente a un rilascio Windows 10 appropriato durante il riavvio notturno della manutenzione. Viene resa disponibile una versione MSI per i clienti che devono gestire manualmente gli aggiornamenti.  

> [!IMPORTANT]
> Durante il periodo di convalida, Microsoft Teams Rooms dispositivi **non** devono essere aggiornati con alcun mezzo alla prossima versione di Windows 10. Ciò include l'override dei criteri di gruppo in atto o l'uso di System Center o di altri servizi di gestione dei dispositivi di terze parti. Uno di questi può causare problemi per l'app Microsoft Teams Room o lasciare i dispositivi inutilizzabili.  

La tabella seguente mostra le versioni consigliate e supportate di Windows 10 verificate per supportare Microsoft Teams Rooms. Tutte le date sono elencate nel formato ISO 8601: AAAA-MM-GG.

| Versione | Data disponibilità | stato del supporto Microsoft Teams Rooms                    | Microsoft Teams Rooms Versione minima applicazione | Build del sistema operativo consigliata |
|:--------|:------------------|:--------------------------------------------------------|:--------------------------------------------------|:---------------------|
| 21H2    | 2021-11-16        | Supportati<br>Consigliata                               | 4.12.126.0                                        | 19044.1288           |
| 21H1    | 2021-05-18        | Non supportato                                           | &#x2014;                                          | &#x2014;             |
| 20H2    | 2020-10-20        | Supportati                                               | 4.10.10.0                                         | 19042.631            |
| 2004    | 2020-05-27        | Saltato <br/> Non consigliato &#x2780;                 | &#x2014;                                          | &#x2014;             |
| 1909    | 2019-11-12        | Supportati                                               | 4.5.33.0                                          | 18363.418            |
| 1903    | 2019-05-21        | Non supportato                                           | &#x2014;                                          | &#x2014;             |
| 1809    | 2019-03-28        | Non supportato, <br/>Problemi di compatibilità noti &#x2781; | &#x2014;                                          | &#x2014;             |
| 1803    | 2018-07-10        | Non supportato                                           | &#x2014;                                          | &#x2014;             |
| 1709    | 2018-01-18        | Non supportato                                           | &#x2014;                                          | &#x2014;             |
| 1703    | 2017-07-11        | Non supportato                                           | &#x2014;                                          | &#x2014;             |

non è consigliabile &#x2780; Windows 10 versione 2004 a causa di problemi di compatibilità riscontrati con l'applicazione Microsoft Teams Rooms. Questo problema specifico causa il mancato avvio dell'applicazione Microsoft Teams Rooms dopo il riavvio notturno. 

non è consigliabile &#x2781; Windows 10 versione 1809 a causa di problemi di compatibilità riscontrati con l'applicazione Microsoft Teams Rooms. Questo problema specifico causa il mancato avvio dell'applicazione Microsoft Teams Rooms dopo il riavvio notturno. Questo problema è stato risolto nella versione Windows 10 1903.  

Quando si usa una versione supportata di Windows 10, si riceveranno sempre gli aggiornamenti più recenti per l'app Microsoft Teams Rooms.  


## <a name="related-topics"></a>Argomenti correlati

[Guida Microsoft Teams Rooms](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[note sulla versione di Microsoft Teams Rooms](rooms-release-note.md)

[Piano per Microsoft Teams Rooms](rooms-plan.md)
