---
title: Problemi noti
ms.author: v-lanac
author: lanachin
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
description: Questo articolo illustra i problemi noti per le sale di Microsoft teams, in base all'area delle caratteristiche.
ms.openlocfilehash: e0b22d55de5fcf2fd49cf795497f2cb26c1952cf
ms.sourcegitcommit: 708270f1fecab6b7b44345d57a8e12bc36d19c8b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2020
ms.locfileid: "43102377"
---
# <a name="known-issues"></a>Problemi noti 
 
Questo articolo elenca i problemi noti di Microsoft teams rooms, in base all'area delle caratteristiche.
<!-- If we get word that one of these issues no longer applies, contact meerak@microsoft.com or msmets@microsoft.com and let them know to EoL the corresponding KB  -->

<a name="update"> </a>  
## <a name="update"></a>Aggiornamento 

| Titolo del problema |  Sintomo del comportamento \/ | Soluzione alternativa nota | Articolo KB |
|  ---        |      ---             |   ---            | --- |
|  App obsoleta         |    La console Microsoft teams Rooms Mostra un errore "configurazione di sistema non aggiornata".                |   [Usare lo strumento di ripristino di Microsoft teams rooms](recovery-tool.md)             |  Nessuno |
|  Dispositivo aggiornato alla versione non supportata di Windows 10   |    Dispositivo Windows 10 aggiornato dalla versione 1803 alla versione 1809, che non è supportato. La versione supportata è 1903. |   Questo problema può verificarsi se l'impostazione di [criteri di gruppo o MDM per](https://docs.microsoft.com/windows/deployment/update/waas-configure-wufb) l'impostazione di DeferFeatureUpdatesPeriodinDays, che consente di rinviare gli aggiornamenti delle caratteristiche per un numero specificato di giorni, viene impostata sul massimo di 365 giorni. <br><br> Windows 10 versione 1809 non è supportato con Microsoft teams rooms, mentre la versione 1903 è supportata. Tuttavia, a partire dal 27 marzo 2020, la versione 1809 è superiore a 365 giorni. Se questa impostazione non è cambiata, Windows tenta di installare la versione 1809, che può causare problemi con le sale di Microsoft teams.<br><br>Per evitare questa situazione, **rimuovere** qualsiasi impostazione di criteri di gruppo o MDM per rinviare gli aggiornamenti. In questo modo, Windows si aggiornerà con la versione più recente del sistema operativo supportata. <br><br>**Importante** L'impostazione criteri di gruppo o MDM deve essere **rimossa** (a sinistra non configurata) e **non impostata su 0**. Se il criterio è impostato su 0, Windows prende la versione più recente disponibile che potrebbe non essere supportata. |  Nessuno |

<a name="OS-conflicts"> </a>  
## <a name="user-interface"></a>Interfaccia utente 

| Titolo del problema |  Sintomo del comportamento \/ | Soluzione alternativa nota | Articolo KB |
|  ---        |      ---             |   ---            | --- |
|Tastiera virtuale mancante   | La tastiera virtuale non viene visualizzata quando è necessario immettere le informazioni nelle sale di Microsoft teams. Questo problema si verifica in Windows 10, versione 1903. | Installare l'aggiornamento cumulativo di 2020-04 per Windows 10, versione 1903 per sistemi basati su x64 tramite gli aggiornamenti di Windows.  | Nessuno | 

<a name="Hardware"> </a>  
## <a name="hardware"></a>Hardware

| Titolo del problema |  Sintomo del comportamento \/ | Soluzione alternativa nota | Articolo KB |
|  ---        |      ---             |   ---            |   --- |
| Monitoraggi non rilevati | Quando si eseguono sale di Microsoft teams su un dispositivo Surface Pro (modello 2017), i monitoraggi non vengono rilevati. |  Tenere premuto il pulsante Surface Pro Power per 20 o più secondi. Quando si esegue questa operazione, il dispositivo riavvia e cancella la cache grafica. |[KB4055681](https://support.microsoft.com/help/4055681/monitors-are-not-detected-when-you-run-skype-room-systems-on-a-surface)       | 

<a name="Limits"> </a>
## <a name="limitations-and-expected-behaviors"></a>Limitazioni e comportamenti previsti

***

Microsoft teams Rooms non supporta l'input HDCP, che è stato osservato in modo da causare problemi con la funzionalità di ingesting HDMI (video, audio). Assicurarsi che le opzioni connesse alle sale di Microsoft teams siano disattivate. 

***

Se si desidera che venga visualizzata una parte anteriore della visualizzazione della sala per passare automaticamente a una sorgente video attiva, ad esempio una console MTR, quando la sorgente viene riattivata dalla modalità standby, è necessario che siano soddisfatte determinate condizioni. Questa caratteristica è facoltativa ma supportata dal software Microsoft teams rooms, purché l'hardware sottostante supporti la funzionalità. Un televisore consumer usato come parte anteriore della visualizzazione della sala deve supportare la funzionalità CEC (Consumer Electronics Control) di HDMI.  A seconda del dock o della console selezionato (che potrebbe non supportare la CEC, vedere la documentazione del supporto per il produttore), potrebbe essere necessario un controller dell'area di lavoro, ad esempio un [EXTRON HD CTL 100](https://www.extron.com/article/hdctl100ad) , per abilitare il comportamento desiderato. 

***

Usa sempre una connessione di rete a 1 Gbps cablata per assicurarti di avere la larghezza di banda necessaria. 

***

Se il dispositivo Microsoft teams Rooms perde fiducia nel dominio, non sarà possibile eseguire l'autenticazione nel dispositivo e aprire le impostazioni. Se ad esempio si rimuovono le sale di Microsoft teams dal dominio dopo l'aggiunta di un dominio, l'attendibilità viene persa. La soluzione alternativa consiste nell'eseguire l'accesso con l'account di amministratore locale. 
***
La versione a 64 bit di Windows 10 Enterprise Anniversary Edition (lingua inglese, versione 1607) non è più supportata da Microsoft teams Rooms Release 3.0.12.0. 
***
Microsoft teams Rooms è un'applicazione con più finestre e richiede la connessione di una facciata dello schermo della sala alla porta HDMI del dispositivo, perché l'app funzioni correttamente. Verificare che sia collegato uno schermo HDMI oppure usare un connettore HDMI fittizio se si sta testando e non è ancora stato acquistato uno schermo.
***
<a name="See"> </a>  
## <a name="see-also"></a>Vedere anche

[Guida di Microsoft teams rooms](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Gestire le sale di Microsoft Teams](rooms-manage.md)
