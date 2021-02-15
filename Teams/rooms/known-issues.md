---
title: Problemi noti
ms.author: dstrome
author: dstrome
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
description: L'amministratore può ottenere informazioni su un elenco di problemi noti di Microsoft Teams Room, tra cui l'aggiornamento, l'interfaccia utente, l'hardware, le limitazioni e i comportamenti previsti.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 63a646fa6fb404cb46de889c318181146cb44b2a
ms.sourcegitcommit: 2639da2c9f903a9a82866be9db2b69a705c54200
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2021
ms.locfileid: "50055738"
---
# <a name="known-issues"></a>Problemi noti 
 
Questo articolo elenca i problemi noti relativi alle sale di Microsoft Teams, per area di funzionalità.
<!-- If we get word that one of these issues no longer applies, contact meerak@microsoft.com or msmets@microsoft.com and let them know to EoL the corresponding KB  -->

<a name="update"> </a>  
## <a name="update"></a>Aggiornamento 

| Titolo del problema |  Sintomo \/ di comportamento | Soluzione alternativa nota | Articolo della Knowledge Base |
|  ---        |      ---             |   ---            | --- |
| L'applicazione non viene avviata |  Dopo l'aggiornamento all'applicazione versione 4.4.41.0, il sistema torna a schermo nero o passa alla schermata di accesso dopo pochi minuti. | Seguire la procedura nell'applicazione Microsoft Teams Rooms non viene avviata dopo l'aggiornamento alla versione [4.4.41.0](https://docs.microsoft.com/microsoftteams/troubleshoot/teams-administration/teams-rooms-app-wont-start-after-update) per risolvere il problema.  | Nessuno |
|  La condivisione di contenuti per le riunioni Consob non viene visualizzata a schermo intero         |    Nelle riunioni Skype for Business, le sale con schermo anteriore con impostazioni DPI elevate possono verificarsi problemi quando il contenuto condiviso in una riunione non viene visualizzato a schermo intero sulla parte anteriore della visualizzazione della sala. Questo problema è causato da un problema sottostante nell'API RDP (Remote Desktop Protocol) di Windows 10. | Usare `<WinRTRdpEnabled>` l'impostazione XML per disabilitare l'API RDP di Windows 10 per risolvere il problema. Per disabilitarlo, è necessario specificare il valore come `false` . Per altre informazioni, vedere [Gestione delle impostazioni della console con un file di configurazione XML.](xml-config-file.md#manage-console-settings-with-an-xml-configuration-file) | Nessuno |
|  App non aggiornata         |    La console Sale di Microsoft Teams mostra un errore di "configurazione del sistema non aggiornata".                |   [Usare lo strumento di ripristino Sale di Microsoft Teams](recovery-tool.md)             |  Nessuno |
|  Dispositivo aggiornato alla versione non supportata di Windows 10   |    Dispositivo Windows 10 aggiornato dalla versione 1803 alla versione 1809, che non è supportata. La versione supportata è 1903. |   Questo problema può verificarsi se l'impostazione di Criteri di gruppo o MDM per [l'impostazione DeferFeatureUpdatesPeriodayDays,](https://docs.microsoft.com/windows/deployment/update/waas-configure-wufb) che consente di rinviare gli aggiornamenti delle caratteristiche per un numero specificato di giorni, è impostata su un massimo di 365 giorni. <br><br> Windows 10 versione 1809 non è supportato con Microsoft Teams Room, mentre la versione 1903 è supportata. Tuttavia, a partire dal 27 marzo 2020, la versione 1809 ha più di 365 giorni. Se questa impostazione non viene modificata, Windows prova a installare la versione 1809, il che potrebbe causare problemi con le sale di Microsoft Teams.<br><br>Per evitare questa situazione, rimuovere **qualsiasi** impostazione di Criteri di gruppo o MDM per posticipare gli aggiornamenti. In questo modo Windows può eseguire l'aggiornamento alla versione più recente supportata del sistema operativo. <br><br>**IMPORTANTE** L'impostazione di Criteri di gruppo o MDM deve essere **rimossa** (non configurata) e **non impostata su 0.** Se il criterio è impostato su 0, Windows sfrutta l'ultima versione disponibile che potrebbe non essere supportata. |  Nessuno |



<a name="OS-conflicts"> </a>  
## <a name="user-interface"></a>Interfaccia utente 

| Titolo del problema |  Sintomo \/ di comportamento | Soluzione alternativa nota | Articolo della Knowledge Base |
|  ---        |      ---             |   ---            | --- |
|Tastiera virtuale mancante   | La tastiera virtuale non viene visualizzata quando è necessario immettere informazioni nelle sale di Microsoft Teams. Questo problema si verifica in Windows 10 versione 1903. | Installare l'aggiornamento cumulativo 2020-04 per Windows 10, versione 1903 per sistemi x64 tramite gli aggiornamenti di Windows.  | Nessuno | 

<a name="Hardware"> </a>  
## <a name="hardware"></a>Hardware

| Titolo del problema |  Sintomo \/ di comportamento | Soluzione alternativa nota | Articolo della Knowledge Base |
|  ---        |      ---             |   ---            |   --- |
| Monitor non rilevati | Quando si eseguono sale di Microsoft Teams su un dispositivo Surface Pro (modello 2017), i monitor non vengono rilevati. |  Tieni premuto il pulsante di alimentazione di Surface Pro per 20 o più secondi. Quando si esegue questa operazione, il dispositivo viene riavviato e cancella la cache degli elementi grafici. |[KB4055681](https://support.microsoft.com/help/4055681/monitors-are-not-detected-when-you-run-skype-room-systems-on-a-surface)       | 

<a name="Limits"> </a>
## <a name="limitations-and-expected-behaviors"></a>Limitazioni e comportamenti previsti

**_

Microsoft Teams Room non supporta l'input HDCP, che è stato osservato per causare problemi con la funzionalità di ingestizione HDMI (video, audio). Assicurarsi che gli switch connessi alle sale di Microsoft Teams abbia le opzioni HDCP disattivate. 

_*_

Se si desidera che la visualizzazione anteriore della stanza passare automaticamente a un'origine video attiva (ad esempio una console MTR) quando l'origine si riattiva dalla modalità standby, è necessario che siano soddisfatte determinate condizioni. Questa funzionalità è facoltativa ma supportata dal software Microsoft Teams Rooms, a condizione che l'hardware sottostante supporti la funzionalità. Una TV consumer usata come schermo davanti alla sala deve supportare la funzionalità Consumer Electronics Control (CEC) di HDMI.  A seconda del dock o della console selezionata (che potrebbe non supportare CEC, consulta la documentazione del supporto tecnico del produttore), potrebbe essere necessario un controller come [HD-RX-201-C-E](https://www.crestron.com/Products/Video/HDMI-Solutions/HDMI-Extenders/HD-RX-201-C-E) da Crestron o [Extron HD CTL 100](https://www.extron.com/article/hdctl100ad) da Extron per abilitare il comportamento desiderato. 

_*_

Usa sempre una connessione di rete cablata da 1 Gbps per assicurarti di avere la larghezza di banda necessaria. 

_*_

Se il dispositivo Sale di Microsoft Teams perde la fiducia nel dominio, non sarà possibile eseguire l'autenticazione nel dispositivo e aprire le impostazioni. Ad esempio, se si rimuovono le sale di Microsoft Teams dal dominio dopo che è stato aggiunto al dominio, l'attendibilità va persa. La soluzione alternativa consiste nell'accedere con l'account di amministratore locale. 
_*_ Microsoft Teams Rooms è un'applicazione multi-finestra e richiede la connessione dello schermo anteriore della sala alla porta HDMI del dispositivo, per il corretto funzionamento dell'app. Assicurati di avere uno schermo HDMI connesso o di usare un connettore HDMI fittizio se stai effettuando dei test e non hai ancora acquistato uno schermo.
_** <a name="See"> </a>  
## <a name="see-also"></a>Vedere anche

[Guida di Microsoft Teams Rooms](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Gestire Microsoft Teams Rooms](rooms-manage.md).
