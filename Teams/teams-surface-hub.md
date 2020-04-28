---
title: Distribuire Microsoft teams per Surface Hub
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 12/04/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: jatpatel
description: Informazioni su come installare e configurare l'app team per Surface Hub in modo che i team siano l'applicazione predefinita per le chiamate e le riunioni.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Devices
- seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 589bbfe75f0beea88066b5a6188b1d29c98ddd5f
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905648"
---
<a name="deploy-microsoft-teams-for-surface-hub"></a>Distribuire Microsoft teams per Surface Hub
======================================

Prima di installare teams per Surface Hub, assicurarsi di eseguire le operazioni seguenti:

 □ Verificare che l'hardware, il sistema operativo e gli altri requisiti vengano soddisfatti. Per altre informazioni, vedere la [Guida per gli amministratori di Surface Hub Microsoft](https://docs.microsoft.com/surface-hub/).<br>
 □ Verificare che l'aggiornamento del sistema operativo minimo necessario per i team sia installato- [KB4343889](https://support.microsoft.com/help/4343889).<br>
 □ Assegnare una licenza teams all'account del dispositivo hub.<br>
 □ Se si esegue la transizione da Skype for business online, verificare che all'utente sia assegnata una licenza di teams.

## <a name="install-teams-for-surface-hub-from-the-microsoft-store"></a>Installare Team per Surface Hub da Microsoft Store 

Queste istruzioni sono per l'installazione di teams per Surface Hub da Microsoft Store. 
 
1. Avviare Microsoft Store:<br>
   a. Toccare **Avvia** > **tutte** > **le impostazioni delle**app.<br> b. Toccare **account del dispositivo hub superficie, gestione**.<br>
   c. A sinistra, toccare la scheda **funzionalità & app** .<br> 3D. Sulla destra toccare il pulsante **Apri Store** . 
2. In Microsoft Store cercare *Microsoft teams*. Verrà visualizzato l' **Hub Microsoft teams per Surface** . Toccare il pulsante **Ottieni l'app** per installarlo.  
3. Al termine dell'installazione, riavviare Surface Hub. 

> [!NOTE]
> Non toccare **Avvia** nella pagina dell'elenco dello Store.

## <a name="make-teams-the-default-calling-and-meetings-application"></a>Rendere le squadre l'applicazione predefinita per le chiamate e le riunioni
 
Sono disponibili due opzioni per la configurazione dei criteri di applicazione delle chiamate e delle riunioni predefiniti: 

- **Opzione 1**: configurare tramite chiave USB. 
- **Opzione 2**: configurare tramite MDM, ad esempio Intune.
 
### <a name="option-1-configure-via-usb-key"></a>Opzione 1: configurare tramite chiave USB 
 
I pacchetti si trovano nella pagina di [download](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g). Selezionare quello appropriato per il pacchetto che si sta pianificando di installare e copiarlo in una chiave USB. Il file con estensione ppkg corretto da usare dipende dai criteri di applicazione predefiniti che si desidera applicare nel modo seguente: 

|Numero  |Descrizione  |
|---------|---------|
|0     | App preferita Skype nella schermata Start, riunioni teams disponibile        |
|1     | App squadre preferite nella schermata Start, riunioni Skype disponibili        |
|2     | App esclusive teams nella schermata Start (app Skype non disponibile)        |
 
1. Allegare la chiave USB al dispositivo Surface Hub. 
2. Aprire l'app **Impostazioni** in un dispositivo Surface Hub. 
3. Aprire **Gestione account del dispositivo Surface Hub**.
4. Aprire **Gestione dispositivi**. 
5. Fare clic su **Aggiungi o Rimuovi un pacchetto di provisioning**. 
6. Fare clic su **Aggiungi pacchetto**.
7. Selezionare l'opzione **supporto rimovibile** dal menu a discesa. 
8. Aggiungi il pacchetto <strong>TeamsRTMMode *. ppkg</strong> appropriato copiato in precedenza nella chiave USB. 
9. Riavviare il dispositivo Surface Hub. 
10. Dopo il riavvio del dispositivo, dovresti essere in grado di avviare l'app teams dalla schermata Start e partecipare a una riunione dal calendario. 

### <a name="option-2-configure-via-mdm-such-as-intune"></a>Opzione 2: configurare tramite MDM, ad esempio Intune 

Usare la procedura seguente per configurare i criteri di applicazione delle chiamate e delle riunioni predefiniti tramite Intune. Vedere anche il Blog, [distribuire l'app Microsoft teams per Surface hub usando Intune](https://y0av.me/2018/07/16/deploy-the-microsoft-teams-for-surface-hub-app-using-intune/).

|Impostazione   |Valore    |Descrizione    |
|----------|---------|---------|
|Percorso      | ./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode        |
|Tipo di dati | numero intero (0-2)   |0-app preferita Skype nella schermata Start, riunioni teams disponibili<br>1-app preferite per le squadre nella schermata Start, riunioni Skype disponibili<br>App esclusive 2-teams nella schermata Start (app Skype non disponibile) |
|Operazioni| Ottieni, imposta        |

|Impostazione   |Valore    |
|----------|---------|
|Percorso      | ./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId        |
|Tipo di dati | String-Set String to teams ID Package Application come **Microsoft. MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe! Teams** |
|Operazioni| Ottieni, imposta        |

Riavviare il dispositivo Surface Hub. Dopo il riavvio del dispositivo, dovresti essere in grado di avviare l'app teams dalla schermata Start e partecipare a una riunione dal calendario.

