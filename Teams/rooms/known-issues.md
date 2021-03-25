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
description: L'amministratore può ottenere informazioni su un elenco di problemi noti per Microsoft Teams Rooms, tra cui l'aggiornamento, l'interfaccia utente, l'hardware e le limitazioni e i comportamenti previsti.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 02e7d2411fa1d8a86fe20dcab3013be758f22a21
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117534"
---
# <a name="known-issues"></a>Problemi noti 
 
Questo articolo elenca i problemi noti per Microsoft Teams Rooms, per area di funzionalità.
<!-- If we get word that one of these issues no longer applies, contact meerak@microsoft.com or msmets@microsoft.com and let them know to EoL the corresponding KB  -->

<a name="update"> </a>  
## <a name="update"></a>Aggiornamento 

| Titolo del problema |  Sintomo \/ del comportamento | Soluzione alternativa nota | Articolo della Knowledge Base |
|  ---        |      ---             |   ---            | --- |
| Applicazione non avviata |  Dopo l'aggiornamento alla versione 4.4.41.0 dell'applicazione, il sistema viene avviato sullo schermo nero o passa alla schermata di accesso dopo alcuni minuti. | Seguire la procedura descritta nell'applicazione Microsoft Teams Rooms non viene avviata dopo l'aggiornamento alla [versione 4.4.41.0](/microsoftteams/troubleshoot/teams-administration/teams-rooms-app-wont-start-after-update) per risolvere il problema.  | Nessuno |
|  La condivisione del contenuto delle riunioni SfB non viene visualizzata a schermo intero         |    Nelle riunioni Skype for Business, le sale con schermi davanti alla sala con impostazioni DPI elevate possono verificarsi problemi in cui il contenuto condiviso in una riunione non mostra lo schermo intero nella parte anteriore dello schermo della sala. Questo problema è causato da un problema sottostante nell'API RDP (Remote Desktop Protocol) di Windows 10. | Usare `<WinRTRdpEnabled>` l'impostazione XML per disabilitare l'API RDP di Windows 10 per risolvere il problema. Per disabilitare, è necessario specificare il valore come `false` . Per altre informazioni, vedere [Gestione delle impostazioni della console con un file di configurazione XML.](xml-config-file.md#manage-console-settings-with-an-xml-configuration-file) | Nessuno |
|  App non aggiornata         |    Nella console di Microsoft Teams Rooms viene visualizzato un errore "Configurazione di sistema non aggiornata".                |   [Usare lo strumento di ripristino di Microsoft Teams Rooms](recovery-tool.md)             |  Nessuno |
|  Dispositivo aggiornato alla versione non supportata di Windows 10   |    Dispositivo Windows 10 aggiornato dalla versione 1803 alla versione 1809, che non è supportato. La versione supportata è 1903. |   Questo problema può verificarsi se l'impostazione di Criteri di gruppo o MDM per [l'impostazione DeferFeatureUpdatesPeriodinDays,](/windows/deployment/update/waas-configure-wufb) che consente di posticipare gli aggiornamenti delle funzionalità per un numero di giorni specificato, è impostata su un massimo di 365 giorni. <br><br> Windows 10 versione 1809 non è supportato con Microsoft Teams Rooms, mentre la versione 1903 è supportata. Tuttavia, a partire dal 27 marzo 2020, la versione 1809 ha più di 365 giorni. Se questa impostazione non viene modificata, Windows prova a installare la versione 1809, causando problemi con Microsoft Teams Rooms.<br><br>Per evitare questa situazione, **rimuovere qualsiasi** impostazione di Criteri di gruppo o MDM per posticipare gli aggiornamenti. In questo modo Windows può eseguire l'aggiornamento all'ultima versione supportata del sistema operativo. <br><br>**IMPORTANTE** L'impostazione di Criteri di gruppo o MDM deve essere **rimossa** (non configurata) e **non deve essere impostata su 0.** Se il criterio è impostato su 0, Windows accetta l'ultima versione disponibile che potrebbe non essere supportata. |  Nessuno |



<a name="OS-conflicts"> </a>  
## <a name="user-interface"></a>Interfaccia utente 

| Titolo del problema |  Sintomo \/ del comportamento | Soluzione alternativa nota | Articolo della Knowledge Base |
|  ---        |      ---             |   ---            | --- |
|Tastiera virtuale mancante   | La tastiera virtuale non viene visualizzata quando è necessario immettere informazioni in Microsoft Teams Rooms. Questo problema si verifica in Windows 10, versione 1903. | Installare l'aggiornamento cumulativo 2020-04 per Windows 10, versione 1903 per sistemi basati su x64 tramite gli aggiornamenti di Windows.  | Nessuno | 

<a name="Hardware"> </a>  
## <a name="hardware"></a>Hardware

| Titolo del problema |  Sintomo \/ del comportamento | Soluzione alternativa nota | Articolo della Knowledge Base |
|  ---        |      ---             |   ---            |   --- |
| Monitor non rilevati | Quando si esegue Microsoft Teams Rooms in un dispositivo Surface Pro (Modello 2017), i monitor non vengono rilevati. |  Tieni premuto il pulsante di alimentazione di Surface Pro per 20 o più secondi. In questo caso, il dispositivo si riavvia e cancella la cache grafica. |[KB4055681](https://support.microsoft.com/help/4055681/monitors-are-not-detected-when-you-run-skype-room-systems-on-a-surface)       | 

<a name="Limits"> </a>
## <a name="limitations-and-expected-behaviors"></a>Limitazioni e comportamenti previsti

***

Microsoft Teams Rooms non supporta l'input HDCP, che è stato osservato per causare problemi con la funzionalità di inserimento HDMI (video, audio). Assicurarsi che gli switch connessi alle chat room di Microsoft Teams siano disattivati. 

***

Se si vuole che lo schermo anteriore della sala si sbiliti automaticamente a un'origine video attiva , ad esempio una console MTR, quando la fonte si riattiva dalla modalità standby, è necessario che siano soddisfatte determinate condizioni. Questa funzionalità è facoltativa ma supportata dal software Microsoft Teams Rooms, a condizione che l'hardware sottostante supporti la funzionalità. Una TV consumer usata come schermo davanti alla sala deve supportare la funzionalità Consumer Electronics Control (CEC) di HDMI.  A seconda del dock o della console selezionata (che potrebbe non supportare CEC, vedere la documentazione del supporto del produttore), potrebbe essere necessario un controller come [hd-RX-201-C-E](https://www.crestron.com/Products/Video/HDMI-Solutions/HDMI-Extenders/HD-RX-201-C-E) da Crestron o [Extron HD CTL 100](https://www.extron.com/article/hdctl100ad) da Extron per abilitare il comportamento desiderato. 

***

Usare sempre una connessione di rete cablata a 1 Gbps per garantire la larghezza di banda necessaria. 

***

Se il dispositivo Microsoft Teams Rooms perde la fiducia con il dominio, non sarà possibile eseguire l'autenticazione nel dispositivo e aprire Impostazioni. Ad esempio, se si rimuovono le chat room di Microsoft Teams dal dominio dopo l'accesso al dominio, l'attendibilità viene persa. La soluzione alternativa consiste nell'accedere con l'account di amministratore locale. 
***
Microsoft Teams Rooms è un'applicazione multi-finestra e richiede che la parte anteriore dello schermo della sala sia collegata alla porta HDMI del dispositivo, per il corretto funzionamento dell'app. Assicurarsi di avere collegato uno schermo HDMI o di usare un connettore HDMI fittizio se si sta testando e non si ha ancora acquistato uno schermo.
***
<a name="See"> </a>  
## <a name="see-also"></a>Vedere anche

[Guida di Microsoft Teams Rooms](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Gestire Microsoft Teams Rooms](rooms-manage.md).