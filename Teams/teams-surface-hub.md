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
description: Scopri come installare e configurare l'app Teams per Surface Hub in modo che Teams sia l'applicazione predefinita per chiamate e riunioni.
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
<a name="deploy-microsoft-teams-for-surface-hub"></a>Distribuire Microsoft Teams per Surface Hub
======================================

Prima di installare Teams per Surface Hub, assicurarsi di eseguire le operazioni seguenti:

 □ assicurarsi che siano soddisfatti i requisiti hardware, del sistema operativo e di altro tipo. Per altre informazioni, consulta la guida per gli amministratori [di Microsoft Surface Hub.](https://docs.microsoft.com/surface-hub/)<br>
 □ che sia installato l'aggiornamento minimo del sistema operativo necessario per Teams - [KB4343889.](https://support.microsoft.com/help/4343889)<br>
 □ assegnare una licenza di Teams all'account del dispositivo Hub.<br>
 □ se stai per passare da Skype for Business online, verifica che all'utente sia assegnata una licenza di Teams.

## <a name="install-teams-for-surface-hub-from-the-microsoft-store"></a>Installare Teams per Surface Hub da Microsoft Store 

Queste istruzioni sono per installare Teams per Surface Hub da Microsoft Store. 
 
1. Avviare Microsoft Store:<br>
   a. Toccare **Avvia tutte** le impostazioni  >  **delle**  >  **app.**<br> b. Toccare **l'account del dispositivo Surface Hub, gestione.**<br>
   c. A sinistra toccare la **scheda & funzionalità.**<br> d. A destra toccare il **pulsante Apri** Store. 
2. Da Microsoft Store, cerca *Microsoft Teams.* Verrà visualizzato Microsoft Teams per **Surface Hub.** Toccare il **pulsante Ottieni l'app** per installare.  
3. Al termine dell'installazione, riavvia Surface Hub. 

> [!NOTE]
> Non toccare Avvia **dalla** pagina della presentazione dello Store.

## <a name="make-teams-the-default-calling-and-meetings-application"></a>Impostare Teams come applicazione predefinita per chiamate e riunioni
 
Sono disponibili due opzioni per configurare il criterio predefinito per le applicazioni di chiamata e riunione: 

- **Opzione 1:** configurare tramite chiave USB. 
- **Opzione 2:** eseguire la configurazione con MDM, ad esempio Intune.
 
### <a name="option-1-configure-via-usb-key"></a>Opzione 1: Configurare tramite chiave USB 
 
I pacchetti sono disponibili in questa [pagina di download.](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g) Selezionare quello appropriato per il pacchetto che si prevede di installare e copiarlo in una chiave USB. Il file ppkg corretto da usare dipende dal criterio di applicazione predefinito che si desidera applicare, come indicato di seguito: 

|Numero  |Descrizione  |
|---------|---------|
|0     | App preferita di Skype nella schermata Start, Riunioni di Teams disponibili        |
|1     | App preferita di Teams nella schermata Start, Riunioni Skype disponibili        |
|2     | App esclusiva di Teams nella schermata Start (l'app Skype non è disponibile)        |
 
1. Collega la chiave USB al dispositivo Surface Hub. 
2. Apri **l'app** Impostazioni in un dispositivo Surface Hub. 
3. Aprire **Gestione account dispositivo Surface Hub.**
4. Aprire **Gestione dispositivi.** 
5. Fai **clic su Aggiungi o rimuovi un pacchetto di provisioning.** 
6. Fare **clic su Aggiungi pacchetto.**
7. Selezionare **l'opzione Supporti** rimovibili dal menu a discesa. 
8. Aggiungere il pacchetto <strong>TeamsRTMMode*.ppkg</strong> appropriato copiato in precedenza nella chiave USB. 
9. Riavviare il dispositivo Surface Hub. 
10. Dopo il riavvio del dispositivo, dovrebbe essere possibile avviare l'app Teams dalla schermata Start e partecipare a una riunione dal calendario. 

### <a name="option-2-configure-via-mdm-such-as-intune"></a>Opzione 2: Configurare tramite MDM, ad esempio Intune 

Usare la procedura seguente per configurare il criterio predefinito per le applicazioni di chiamata e riunione tramite Intune. Vedere anche il blog, [Distribuire l'app Microsoft Teams per Surface Hub usando Intune.](https://y0av.me/2018/07/16/deploy-the-microsoft-teams-for-surface-hub-app-using-intune/)

|Impostazione   |Valore    |Descrizione    |
|----------|---------|---------|
|Percorso      | ./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode        |
|Tipo di dati | numero intero (0-2)   |0 - App preferita di Skype nella schermata Start, Riunioni di Teams disponibili<br>1 - App preferita di Teams nella schermata Start, Riunioni Skype disponibili<br>2 - App esclusiva di Teams nella schermata Start (app Skype non disponibile) |
|Operazioni| Ottieni, Imposta        |

|Impostazione   |Valore    |
|----------|---------|
|Percorso      | ./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId        |
|Tipo di dati | stringa - impostare la stringa su ID pacchetto dell'applicazione Teams **come Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe! Teams** |
|Operazioni| Ottieni, Imposta        |

Riavviare il dispositivo Surface Hub. Dopo il riavvio del dispositivo, dovrebbe essere possibile avviare l'app Teams dalla schermata Start e partecipare a una riunione dal calendario.

