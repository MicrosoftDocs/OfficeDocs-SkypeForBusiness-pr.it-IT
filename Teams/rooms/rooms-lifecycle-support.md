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
description: Questo articolo illustra il supporto del ciclo di vita per le sale di Microsoft teams.
ms.openlocfilehash: 0f445bf2500a01bf8ffddae569d176229bdcfde5
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41825914"
---
# <a name="microsoft-teams-rooms-app-version-support"></a>Supporto per la versione dell'app Microsoft teams rooms
 
L'app Microsoft teams Rooms ottiene gli aggiornamenti alcune volte all'anno. Ogni aggiornamento supportato per dodici (12) mesi dalla data di rilascio per la disponibilità generale (GA). Il supporto tecnico è disponibile per gli interi dodici (12) mesi. La struttura di supporto è tuttavia dinamica, con due fasi distinte che dipendono dalla disponibilità della versione più recente:

- \- **Fase di manutenzione e aggiornamenti critici** quando si esegue la versione più recente dell'app Microsoft teams rooms, vengono visualizzati aggiornamenti periodici che contengono aggiornamenti della *sicurezza e della manutenzione* .

- La \- **fase aggiornamenti della sicurezza solo** quando viene rilasciata una nuova versione dell'app Microsoft teams rooms, le versioni precedenti dell'app hanno un livello di supporto ridotto con *gli aggiornamenti della sicurezza solo* per il resto del ciclo di vita di dodici (12) mesi.

> [!NOTE]
> La versione più recente è sempre nella fase di manutenzione e aggiornamenti critici. Quando si verifica un errore di codice che garantisce un aggiornamento critico, è necessario che sia installata anche la versione più recente per ricevere una correzione. Tutte le altre versioni supportate saranno idonee solo per ricevere gli aggiornamenti della sicurezza.

Tutti i supporti terminano dopo la scadenza del ciclo di vita di dodici (12) mesi per una versione o se da allora sono stati rilasciati più di due aggiornamenti. I clienti devono quindi eseguire l'aggiornamento a una versione supportata.

Tutte le versioni sono elencate nelle [Note sulla versione di Microsoft teams Rooms](rooms-release-note.md).

## <a name="windows-10-release-support"></a>Supporto per Windows 10 Release

Le sale di Microsoft teams richiedono gli SKU Enterprise di Windows 10 o Windows 10 Enterprise in opzioni di manutenzione canali semestrale. Queste altre edizioni di Windows 10 non sono supportate:

- Windows 10 Enterprise Branch Servicing a lungo termine (LTSB)/edizioni LTSC (Long Term Servicing Channel)
- Windows 10 Internet of Things (molto) Enterprise LTSB/LTSC Editions
- qualsiasi altra edizione di Windows, ad esempio Windows 10 Pro o Home Edition

Un aggiornamento delle funzionalità di Windows 10 non viene offerto o aggiornato nei dispositivi Microsoft teams Rooms immediatamente. Un ritardo intenzionale fino a sei mesi dopo la data di disponibilità generale pubblicata nella pagina delle [informazioni sulla versione di Windows 10](https://docs.microsoft.com/windows/release-information/) . Il tempo di ritardo viene usato per convalidare la compatibilità delle versioni di Windows 10 per l'applicazione sale di Microsoft teams, l'hardware del dispositivo e le periferiche audio video certificate. La convalida inizia e continua durante lo sviluppo attivo di ogni versione principale di Windows 10. È necessario un tempo aggiuntivo per verificare che tutti i produttori di dispositivi abbiano creato immagini aggiornate per i propri dispositivi e che Microsoft teams sia in grado di certificare e testare tali immagini. Durante il periodo di convalida, l'app Microsoft teams room usa i [criteri di gruppo di Windows Update for business](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) per ritardare gli aggiornamenti delle funzionalità di Windows 10. Dopo che i problemi di compatibilità vengono trovati e risolti, il blocco viene revocato tramite l'aggiornamento dei criteri di gruppo tramite una nuova versione dell'app in Windows Store. I dispositivi che eseguono l'app Microsoft teams Rooms vengono aggiornati automaticamente in una versione di Windows 10 appropriata durante il riavvio della manutenzione notturna. Una versione MSI viene resa disponibile per i clienti che desiderano gestire manualmente gli aggiornamenti.  

> [!IMPORTANT]
> Durante il periodo di convalida, i dispositivi Microsoft teams Rooms **non** devono essere aggiornati alla versione successiva di Windows 10 con qualsiasi mezzo. Ciò include l'override dei criteri di gruppo in posizione o l'uso di System Center o di altri servizi di gestione dei dispositivi di terze parti. Qualsiasi di queste operazioni può causare problemi per l'applicazione della sala Microsoft teams o può abbandonare i dispositivi inutilizzabili.  

La tabella seguente mostra le versioni consigliate e supportate di Windows 10 verificate per supportare le sale di Microsoft teams. Tutte le date sono elencate nel formato ISO 8601: AAAA-MM-DD.

|Versione  |Data di disponibilità   |Stato supporto di Microsoft teams rooms   |Versione minima dell'applicazione di Microsoft teams rooms | Build del sistema operativo consigliata  |
|:---  |:---       |:---                                  |:---     |:---     |
| 1909 |2019-11-12 |Attualmente in fase di convalida <br/>Non raccomandato|&#x2014; |&#x2014; |
| 1903 |2019-05-21 |&#x2780; supportate <br/>Consigliato  |4.2.4.0 |18362,356 |
| 1809 |2019-03-28 |Ignorato <br/>&#x2781; non consigliato|&#x2014; |&#x2014; |
| 1803 |2018-07-10 |Supportati                             |4.1.22.0 |17134,191|
| 1709 |2018-01-18 |Non supportato                         |&#x2014; |&#x2014; |
| 1703 |2017-07-11 |Non supportato                         |&#x2014; |&#x2014; |
||||||

&#x2780; Windows 10 1903 non è disponibile per i dispositivi Crestron Flex a causa di un problema con un driver di dispositivo grafico Intel. Windows 10 1903 non verrà offerto a questi dispositivi. Gli utenti non devono aggiornare questi dispositivi a 1903 e mantenerli in Windows 10 1803 fino a quando non viene reso disponibile un aggiornamento del driver grafico da Crestron. 

&#x2781; la versione di Windows 10 1809 non è consigliata a causa di problemi di compatibilità trovati con l'applicazione Microsoft teams rooms. Questo problema specifico fa in modo che l'applicazione sale di Microsoft teams non inizi dopo il riavvio notturno. Questo problema è stato risolto nella versione di Windows 10 1903.  

Quando usi una versione supportata di Windows 10, otterrai sempre gli aggiornamenti delle applicazioni più recenti per l'app Microsoft teams rooms.  

## <a name="see-also"></a>Vedere anche

[Guida di Microsoft teams rooms](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Note sulla versione di Microsoft teams rooms](rooms-release-note.md)

[Pianificare le sale di Microsoft Teams](rooms-plan.md)
