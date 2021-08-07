---
title: Impostare l Microsoft Teams'interfaccia utente dei dispositivi Android
ms.author: mitressl
author: flinchbot
manager: leopaiv
audience: ITPro
appliesto:
- Microsoft Teams
ms.reviewer: ''
ms.topic: article
ms.service: msteams
localization_priority: Normal
ms.collection:
- M365-collaboration
description: Scopri come impostare l'interfaccia utente nei Teams Android.
ms.openlocfilehash: f743a0f51015e7bd8fdabd41d120a187774c3370
ms.sourcegitcommit: f3c2559a89e1c4b3514e102cf94c38a697b4bc57
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2021
ms.locfileid: "53725690"
---
# <a name="set-microsoft-teams-android-devices-user-interface"></a>Impostare l Microsoft Teams'interfaccia utente dei dispositivi Android

Microsoft Teams I dispositivi Android possono visualizzare un'interfaccia utente specifica in base al tipo di licenza assegnata all'account di accesso. È possibile eseguire l'override di questo comportamento e controllare l'interfaccia visualizzata. Questo articolo descrive in dettaglio come viene scelta l'interfaccia utente predefinita e come è possibile modificare l'interfaccia usando un criterio di PowerShell.

Sono disponibili tre tipi di interfacce utente nei Teams Android:

1. Utente
2. Area comune
3. Riunione

Se si assegna una licenza utente [a](/microsoftteams/user-access) un account, ad esempio una licenza E3 o E5, il dispositivo Teams visualizza l'interfaccia utente finale predefinita, completamente in primo piano per la maggior parte degli scenari utente. Tuttavia, se un dispositivo esegue una funzione specifica, ad esempio un telefono di area comune o una sala riunioni, esistono interfacce utente specifiche per questi utilizzi.

Le tre immagini seguenti mostrano come cambia l'interfaccia utente in base alla licenza assegnata all'account utente. Nella prima immagine all'account utente viene assegnata una licenza E5. Si tratta di una licenza utente, quindi il dispositivo mostra l'interfaccia utente finale predefinita:

:::image type="content" source="../media/TeamsAndroidDevices-UserMode1.jpg" alt-text="Interfaccia in modalità utente":::

In questa immagine all'account utente è stata assegnata una [licenza per il telefono dell'area comune.](/microsoftteams/set-up-common-area-phones) I telefoni dell'area comune vengono usati principalmente per effettuare e ricevere chiamate telefoniche. Di conseguenza, la tastiera del telefono viene visualizzata sullo schermo:

:::image type="content" source="../media/TeamsAndroidDevices-CAP1.jpg" alt-text="Interfaccia telefonica dell'area comune":::

Infine, questa immagine mostra un account utente a cui è assegnata Microsoft Teams Rooms [licenza Standard.](/MicrosoftTeams/rooms/rooms-licensing) Teams Rooms licenze sono destinate a essere usate nelle sale riunioni o negli spazi condivisi, quindi l'interfaccia utente cambia per semplificare la partecipazione a una riunione mostrando la visualizzazione calendario:

:::image type="content" source="../media/TeamsAndroidDevices-Meeting.jpg" alt-text="Interfaccia riunione":::

> [!NOTE]
> La modifica dell'interfaccia utente non influisce sulla possibilità di usare altre funzionalità con licenza. Ad esempio, anche se la visualizzazione predefinita della licenza Team Rooms è la visualizzazione calendario, è comunque possibile effettuare e ricevere chiamate PSTN (Public Switch Telephone Network) se l'account è correttamente concesso in licenza e configurato.

> [!IMPORTANT]
> Ci sono altri elementi dell'interfaccia che cambiano. Ad esempio, per impedire agli utenti finali di disconnettersi da un telefono dell'area comune o da un dispositivo della sala riunioni, l'opzione "Disconnetta" in questi dispositivi viene spostata in una parte del menu delle impostazioni che richiede le autorizzazioni di amministratore per l'accesso.

## <a name="override-automatic-user-interface-detection"></a>Ignorare il rilevamento automatico dell'interfaccia utente

In alcuni casi, è possibile scegliere di assegnare una licenza a un account che non corrisponde all'uso previsto. Ad esempio, è possibile assegnare una licenza utente a un account destinato ad accedere a Teams Rooms su Android. Per impostazione predefinita, viene visualizzata l'interfaccia utente finale invece dell'interfaccia della sala riunioni. Per ignorare l'interfaccia predefinita, creare un nuovo criterio Teams [ip Telefono](/powershell/module/skype/new-csteamsipphonepolicy?view=skype-ps) e applicarlo a tale account.

> [!NOTE]
> La licenza assegnata all'account utente deve avere almeno gli stessi diritti di licenza dell'interfaccia utente desiderata. La licenza common area Telefono consente solo l'interfaccia utente del telefono area comune. La licenza della sala riunioni consente di utilizzare le interfacce utente della sala riunioni e del telefono dell'area comune. Una licenza E3 o E5 supporta tutte le modalità di accesso.

Di seguito è riportato un esempio di come ignorare il rilevamento automatico delle licenze. In questo esempio si supponga che a un account della risorsa sala riunioni denominato conf-adams@contoso.com sia stata assegnata una licenza E3. Quando l'account è connesso, si vuole che gli utenti vedano l'interfaccia utente della sala riunioni.

### <a name="create-a-new-policy-and-assign-to-user"></a>Creare un nuovo criterio e assegnarlo all'utente

1. Avviare una sessione Windows PowerShell remota e connettersi a Microsoft Teams usando il cmdlet seguente:

    ``` Powershell
    Connect-MicrosoftTeams
    ```

2. Creare un nuovo criterio Teams ip Telefono e impostare la modalità di accesso su "MeetingSignIn":

   ``` Powershell
   New-CsTeamsIPPhonePolicy –Identity 'Meeting Sign in' –Description 'Meeting Sign In Phone Policy' -SignInMode 'MeetingSignIn'

   ```

3. Ora è possibile assegnare questo nuovo criterio all'account delle risorse della sala riunioni:

   ``` Powershell
   Grant-CsTeamsIPPhonePolicy –Identity 'conf-adams@contoso.com' –PolicyName 'Meeting Sign In'
   ```

Dopo aver concesso il criterio all'account delle risorse della sala riunioni, è necessario attendere la replica dell'assegnazione dei criteri. Dovrai anche disconnetterti dal dispositivo e accedere di nuovo.
