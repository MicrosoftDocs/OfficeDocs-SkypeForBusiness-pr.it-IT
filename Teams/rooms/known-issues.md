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
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
description: L'amministratore può ottenere informazioni su un elenco di problemi noti per Microsoft Teams Rooms, tra cui aggiornamento, interfaccia utente, hardware e limitazioni e comportamenti previsti.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 72d80d930a8c140e6c2c00917a08cf69398fd4b1
ms.sourcegitcommit: badcd3abeed138c330ee98d739eac5bbc5c0bfae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/14/2021
ms.locfileid: "61441126"
---
# <a name="known-issues"></a>Problemi noti 
 
Questo articolo elenca i problemi noti di Microsoft Teams Rooms per area funzionale.
<!-- If we get word that one of these issues no longer applies, contact meerak@microsoft.com or msmets@microsoft.com and let them know to EoL the corresponding KB  -->

<a name="update"> </a>  
## <a name="update"></a>Update 

| Titolo problema |  Comportamento \/ Sintomo | Soluzione alternativa nota | Articolo della Knowledge Base |
|  ---        |      ---             |   ---            | --- |
| Video partecipante della raccolta divisa   | Nella modalità di visualizzazione a due fronti della sala, quando non è presente contenuto condiviso in una riunione con più di 9 partecipanti video remoti, un video su uno schermo frontale della sala con l'anteprima automatica potrebbe essere visualizzato come audio a causa di un problema noto. Inoltre, un numero inferiore di partecipanti all'audio rispetto al numero effettivo di partecipanti audio viene visualizzato su due schermi front of Room. | Il problema verrà risolto in un aggiornamento futuro. | Nessuno |
| L'applicazione non viene avviata |  Dopo l'aggiornamento alla versione 4.4.41.0 dell'applicazione, il sistema viene avviato sullo schermo nero o passa alla schermata di accesso dopo pochi minuti. | Segui la procedura descritta in [applicazione Microsoft Teams Rooms non viene avviata dopo l'aggiornamento alla versione 4.4.41.0](/microsoftteams/troubleshoot/teams-administration/teams-rooms-app-wont-start-after-update) per risolvere questo problema.  | Nessuno |
|  Volume di riunioni basso dopo la condivisione del contenuto         |   I dispositivi Microsoft Teams Rooms su Windows 10 esperienza 20H2 hanno ridotto il volume di contenuti multimediali e riunioni dopo la condivisione di contenuti tramite HDMI in sala. Questo è causato da un problema audio in Windows 10 20H2. | La correzione per questo problema è disponibile nella versione [dell'applicazione 4.9.12.0.](/microsoftteams/rooms/rooms-release-note#49120-7282021) | Nessuno |
|  App non aggiornato         |    La console di Microsoft Teams Rooms mostra un errore "configurazione del sistema non aggiornata".                |   [Utilizza lo strumento di ripristino di Microsoft Teams Rooms](recovery-tool.md)             |  Nessuno |
|  Il dispositivo è stato aggiornato alla versione non supportata di Windows 10   |    Dispositivo con Windows 10 aggiornato dalla versione 1803 alla versione 1809, che non è supportato. La versione supportata è la 1903. |   Questo può verificarsi se l'impostazione [Criteri di gruppo o MDM per DeferFeatureUpdatesPeriodinDays](/windows/deployment/update/waas-configure-wufb), che consente di rinviare gli aggiornamenti delle funzionalità per un numero specificato di giorni, è configurata a un massimo di 365 giorni. <br><br> Windows 10 versione 1809 non è supportata con Microsoft Teams Rooms, mentre la versione 1903 è supportata. Tuttavia, a partire dal 27 marzo 2020, la versione 1809 ha più di 365 giorni. Se questa impostazione non viene modificata, Windows cerca di installare la versione 1809, causando problemi con Microsoft Teams Rooms.<br><br>Per evitare questa situazione, **rimuovi** qualsiasi impostazione Criteri di gruppo o MDM per il rinvio degli aggiornamenti. In questo modo Windows può eseguire l'aggiornamento alla versione del sistema operativo più recente supportata. <br><br>**IMPORTANTE:** L'impostazione di Criteri di gruppo o MDM deve essere **rimossa** (non configurata) e **non deve essere impostata su 0.** Se il criterio è impostato su 0, Windows accetta la versione disponibile più recente che potrebbe non essere supportata. |  Nessuno |



<a name="OS-conflicts"> </a>  
## <a name="user-interface"></a>Interfaccia utente 

| Titolo problema |  Comportamento \/ Sintomo | Soluzione alternativa nota | Articolo della Knowledge Base |
|  ---        |      ---             |   ---            | --- |
|Tastiera virtuale mancante   | La tastiera virtuale non viene visualizzata quando è necessario immettere informazioni in Microsoft Teams Rooms. Questo problema si verifica in Windows 10, versione 1903. | Installa l'aggiornamento cumulativo 2020-04 per Windows 10, versione 1903 per sistemi basati su x64 tramite gli aggiornamenti di Windows.  | Nessuno | 

<a name="Hardware"> </a>  
## <a name="hardware"></a>Hardware

| Titolo problema |  Comportamento \/ Sintomo | Soluzione alternativa nota | Articolo della Knowledge Base |
|  ---        |      ---             |   ---            |   --- |
| Monitor non rilevati | Quando esegui Microsoft Teams Rooms in un dispositivo Surface Pro (modello 2017), i monitor non vengono rilevati. |  Tieni premuto il pulsante di alimentazione Surface Pro per 20 o più secondi. Quando esegui questa operazione, il dispositivo viene riavviato e la cache grafica viene cancellata. |[KB4055681](https://support.microsoft.com/help/4055681/monitors-are-not-detected-when-you-run-skype-room-systems-on-a-surface)       | 

<a name="Limits"> </a>
## <a name="limitations-and-expected-behaviors"></a>Limitazioni e comportamenti previsti

***

Microsoft Teams Rooms non supporta l'input HDCP, che è stato osservato per causare problemi con la funzionalità di inserimento HDMI (video, audio). Verifica che i commutatori connessi a Microsoft Teams Rooms abbiano le opzioni HDCP disattivate. 

***

Se desideri che un display frontale passi automaticamente a un’origine video attiva (come una console MTR) quando l’origine si sveglia dalla modalità standby, devono essere soddisfatte alcune condizioni. Questa funzionalità è facoltativa ma supportata dal software Microsoft Teams Rooms, purché l'hardware sottostante supporti la funzionalità. Un televisore utente usato come display frontale della sala deve supportare la funzionalità Consumer Electronics Control (CEC) di HDMI.  A seconda del dock o della console selezionati (che potrebbe non supportare CEC, fare riferimento alla documentazione di supporto del produttore), potrebbe essere necessario un controller come un [HD-RX-201-C-E](https://www.crestron.com/Products/Video/HDMI-Solutions/HDMI-Extenders/HD-RX-201-C-E) da Crestron o [Extron HD CTL 100](https://www.extron.com/article/hdctl100ad) da Extron per abilitare il comportamento desiderato.

Inoltre, una TV consumer usata come schermo anteriore della sala può causare problemi di stabilità con Microsoft Teams Rooms software. Ciò è dovuto all'implementazione incoerente delle modalità di standby, alla selezione dell'origine video attiva e alla comunicazione di informazioni EDID difettose al Microsoft Teams Rooms dispositivo. I sintomi noti sono uno schermo nero/grigio nella parte anteriore dello schermo della sala o la console di Microsoft Teams Rooms che non risponde dopo il risveglio dalla modalità standby.  Se si verificano problemi durante l'uso di televisori consumer, è consigliabile installare un controller EDID configurabile o un emulatore EDID, ad esempio [l'HD-RX-201-C-E](https://www.crestron.com/Products/Video/HDMI-Solutions/HDMI-Extenders/HD-RX-201-C-E) di Crestron o [dr-EDID Emulator](https://fsrinc.com/fsr-products/product/dr-edid-manager-learner/category_pathway-143) da FSR Video Products Group.

***

Usa sempre una connessione di rete cablata da 1 Gbps per assicurarti di avere la larghezza di banda necessaria. 

***

Se il tuo dispositivo Microsoft Teams Rooms perde l'attendibilità con il dominio, non sarà possibile eseguire l'autenticazione nel dispositivo e aprire Impostazioni. Ad esempio, se si rimuove Microsoft Teams Rooms dal dominio dopo che è stato aggiunto al dominio, l'attendibilità viene persa. La soluzione alternativa consiste nell'accedere con l'account amministratore locale. 
***
Microsoft Teams Rooms è un'applicazione a più finestre e richiede che un display frontale della sala sia connesso alla porta HDMI del dispositivo, affinché l'app funzioni correttamente. Verifica di avere un display HDMI connesso o di usare un plug-in HDMI fittizio se stai testando e non si è ancora acquistato un display.
***
<a name="See"> </a>  
## <a name="see-also"></a>Vedere anche

[Guida Microsoft Teams Rooms](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Gestire Microsoft Teams Rooms](rooms-manage.md).
