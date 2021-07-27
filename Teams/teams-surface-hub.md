---
title: Distribuire Microsoft Teams per Surface Hub
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 12/04/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: jatpatel
description: Informazioni su come installare e configurare l'app Teams per Surface Hub in modo che Teams sia l'applicazione predefinita per chiamate e riunioni.
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
ms.openlocfilehash: d65f94b3f1e71a59ac2debc04828c5fa25f000f7
ms.sourcegitcommit: b387296c043fcf10fba7b9ef416328383e54a565
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/26/2021
ms.locfileid: "53587005"
---
# <a name="deploy-microsoft-teams-for-surface-hub"></a>Distribuire Microsoft Teams per Surface Hub

Prima di installare Teams per Surface Hub, assicurarsi di eseguire le operazioni seguenti:

 □ assicurarsi che siano soddisfatti i requisiti hardware, del sistema operativo e di altro tipo. Per altre informazioni, vedere la guida [Microsoft Surface Hub per gli amministratori.](/surface-hub/)<br>
 □ verificare che sia installato l'aggiornamento minimo del sistema operativo Teams - [KB4343889](https://support.microsoft.com/help/4343889).<br>
 □ assegnare una licenza Teams all'account del dispositivo Hub.<br>
 □ Se si esegue la transizione da Skype for Business Online, verificare che all'utente sia assegnata una licenza Teams licenza.

## <a name="install-teams-for-surface-hub-from-the-microsoft-store"></a>Installare Teams per Surface Hub dal Microsoft Store 

Queste istruzioni sono per l'installazione di Teams per Surface Hub dal Microsoft Store. 
 
1. Avviare il Microsoft Store:<br>
   a. Toccare **Avvia**  >  **tutte le app**  >  **Impostazioni**.<br> b. Toccare **Surface Hub account del dispositivo, gestione**.<br>
   c. A sinistra toccare la **scheda App & funzionalità.**<br> d. A destra, tocca il **pulsante Apri Store.** 
2. Nell'elenco Microsoft Store cercare *Microsoft Teams*. Verranno **Microsoft Teams le Surface Hub** per i file. Toccare il **pulsante Scarica l'app** per installare.  
3. Al termine dell'installazione, riavviare il Surface Hub. 

> [!NOTE]
> Non toccare Avvia **dalla** pagina della presentazione dello Store.

## <a name="make-teams-the-default-calling-and-meetings-application"></a>Impostare Teams'applicazione predefinita per chiamate e riunioni
 
Sono disponibili due opzioni per configurare i criteri predefiniti per le chiamate e le riunioni: 

- **Opzione 1**: Configura tramite chiave USB. 
- **Opzione 2:** configurare tramite MDM, ad esempio Intune.
 
### <a name="option-1-configure-via-usb-key"></a>Opzione 1: Configurare tramite chiave USB 
 
I pacchetti sono disponibili in questa [pagina di download.](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g) Selezionare quello appropriato per il pacchetto che si prevede di installare e copiarlo in una chiave USB. Il file ppkg corretto da usare dipende dai criteri di applicazione predefiniti che si desidera applicare nel modo seguente: 

|Numero  |Descrizione  |
|---------|---------|
|0     | Skype app preferita nella schermata Start, Teams riunioni disponibili        |
|1     | Teams'app preferita nella schermata Start, Skype riunioni disponibili        |
|2     | Teams'app esclusiva nella schermata Start (Skype'app non disponibile)        |
 
1. Collegare la chiave USB al Surface Hub dispositivo. 
2. Aprire **l Impostazioni app** in un dispositivo Surface Hub dispositivo. 
3. Aprire **Surface Hub gestione dell'account del dispositivo**.
4. Aprire **Gestione dispositivi**. 
5. Fare **clic su Aggiungi o rimuovi un pacchetto di provisioning.** 
6. Fare clic **su Aggiungi pacchetto**.
7. Selezionare **l'opzione Supporti** rimovibili dal menu a discesa. 
8. Aggiungere il pacchetto <strong>TeamsRTMMode*.ppkg</strong> appropriato copiato in precedenza nella chiave USB. 
9. Riavviare il Surface Hub dispositivo. 
10. Dopo il riavvio del dispositivo, dovrebbe essere possibile avviare l'app Teams dalla schermata Start e partecipare a una riunione dal calendario. 

### <a name="option-2-configure-via-mdm-such-as-intune"></a>Opzione 2: Configurare tramite MDM, ad esempio Intune 

Usare quanto segue per configurare i criteri predefiniti per le chiamate e le riunioni tramite Intune. Vedere anche il blog Distribuire [l'app Microsoft Teams per Surface Hub tramite Intune.](https://y0av.me/2018/07/16/deploy-the-microsoft-teams-for-surface-hub-app-using-intune/)

|Impostazione   |Valore    |Descrizione    |
|----------|---------|---------|
|Percorso      | ./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode        |
|Tipo di dati | Numero intero (0-2)   |0 - Skype app preferita nella schermata Start, Teams riunioni disponibili<br>1 - Teams app preferita nella schermata Start, Skype riunioni disponibili<br>2 - Teams app esclusiva nella schermata Start (Skype'app non disponibile) |
|Operazioni| Ottieni, Imposta        |

|Impostazione   |Valore    |
|----------|---------|
|Percorso      | ./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId        |
|Tipo di dati | stringa: impostare stringa su Teams ID pacchetto dell'applicazione **come Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe!Teams** |
|Operazioni| Ottieni, Imposta        |

Riavviare il Surface Hub dispositivo. Dopo il riavvio del dispositivo, dovrebbe essere possibile avviare l'app Teams dalla schermata Start e partecipare a una riunione dal calendario.