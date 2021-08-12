---
title: Impostare l'interfaccia utente di Microsoft Teams sui dispositivi Android
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
ms.openlocfilehash: d3b625e4a54a6a9dcb75d0d1518a65b3e91c23185736672458b0fa1bbd6d55e1
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54327352"
---
# <a name="set-microsoft-teams-android-devices-user-interface"></a>Impostare l'interfaccia utente di Microsoft Teams sui dispositivi Android

Microsoft Teams I dispositivi Android possono visualizzare un'interfaccia utente specifica in base al tipo di licenza assegnata all'account connesso. Puoi eseguire l'override di questo comportamento e controllare quale interfaccia viene visualizzata. In questo articolo viene descritto in dettaglio come viene scelta l'interfaccia utente predefinita e come è possibile modificare l'interfaccia utilizzando un criterio di PowerShell.

Esistono tre tipi di interfacce utente nei Teams Android:

1. Utente
2. Area comune
3. Riunione

Se assegni una licenza utente [a](/microsoftteams/user-access) un account, ad esempio una licenza E3 o E5, nel dispositivo Teams verrà visualizzata l'interfaccia utente finale predefinita completamente disponibile per la maggior parte degli scenari utente. Tuttavia, se un dispositivo esegue una funzione specifica, ad esempio un telefono di area comune o una sala riunioni, esistono interfacce utente specifiche per questi utilizzi.

Le tre immagini seguenti mostrano come cambia l'interfaccia utente in base alla licenza assegnata all'account utente. Nella prima immagine all'account utente viene assegnata una licenza E5. Si tratta di una licenza utente, quindi il dispositivo mostra l'interfaccia utente finale predefinita:

:::image type="content" source="../media/TeamsAndroidDevices-UserMode1.jpg" alt-text="Interfaccia in modalità utente":::

In questa immagine, all'account utente è stata assegnata una [licenza telefonica di area comune.](/microsoftteams/set-up-common-area-phones) I telefoni delle aree comuni vengono utilizzati principalmente per effettuare e ricevere chiamate telefoniche. Di conseguenza, sul display viene visualizzata la tastiera del telefono:

:::image type="content" source="../media/TeamsAndroidDevices-CAP1.jpg" alt-text="Interfaccia telefonica di area comune":::

Infine, questa immagine mostra un account utente a [cui è assegnata Microsoft Teams Rooms licenza Standard.](/MicrosoftTeams/rooms/rooms-licensing) Teams Rooms licenze sono destinate a essere utilizzate in sale riunioni o spazi condivisi, quindi l'interfaccia utente cambia per semplificare la partecipazione a una riunione mostrando la visualizzazione calendario:

:::image type="content" source="../media/TeamsAndroidDevices-Meeting.jpg" alt-text="Interfaccia riunione":::

> [!NOTE]
> La modifica dell'interfaccia utente non influisce sulla possibilità di usare altre funzionalità con licenza. Ad esempio, anche se la visualizzazione predefinita della licenza di Team Rooms è la visualizzazione calendario, è comunque possibile effettuare e ricevere chiamate PSTN (Public Switch Telephone Network) se l'account è correttamente concesso in licenza e configurato.

> [!IMPORTANT]
> Esistono altri elementi dell'interfaccia che cambiano. Ad esempio, per impedire agli utenti finali di disconnettersi da un telefono dell'area comune o da un dispositivo della sala riunioni, l'opzione "Disconnetta" in questi dispositivi viene spostata in una parte del menu delle impostazioni che richiede le autorizzazioni di amministratore per accedere.

## <a name="override-automatic-user-interface-detection"></a>Ignorare il rilevamento automatico dell'interfaccia utente

In alcuni casi, puoi scegliere di assegnare una licenza a un account che non corrisponde all'uso previsto. Ad esempio, puoi assegnare una licenza utente a un account destinato ad accedere a Teams Rooms su Android. Per impostazione predefinita, verrà visualizzata l'interfaccia utente finale anziché l'interfaccia della sala riunioni. Per ignorare l'interfaccia predefinita, creare un nuovo criterio [Teams ip Telefono](/powershell/module/skype/new-csteamsipphonepolicy?view=skype-ps) e applicarlo a tale account.

> [!NOTE]
> La licenza assegnata all'account utente deve avere almeno gli stessi diritti di licenza dell'interfaccia utente desiderata. La licenza dell Telefono area comune consente solo l'interfaccia utente del telefono dell'area comune. La licenza della sala riunioni consente di utilizzare le interfacce utente della sala riunioni e del telefono dell'area comune. Una licenza E3 o E5 supporta tutte le modalità di accesso.

Di seguito è riportato un esempio di come ignorare il rilevamento automatico delle licenze. In questo esempio si supponga che a un account della risorsa sala riunioni denominato conf-adams@contoso.com sia stata assegnata una licenza E3. Quando questo account è connesso, si desidera che gli utenti vedano l'interfaccia utente della sala riunioni.

### <a name="create-a-new-policy-and-assign-to-user"></a>Creare un nuovo criterio e assegnarlo all'utente

1. Avviare una sessione Windows PowerShell remota e connettersi a Microsoft Teams utilizzando il cmdlet seguente:

    ``` Powershell
    Connect-MicrosoftTeams
    ```

2. Creare un nuovo Teams ip Telefono e impostare la modalità di accesso su "MeetingSignIn":

   ``` Powershell
   New-CsTeamsIPPhonePolicy –Identity 'Meeting Sign in' –Description 'Meeting Sign In Phone Policy' -SignInMode 'MeetingSignIn'

   ```

3. È ora possibile assegnare questo nuovo criterio all'account della risorsa sala riunioni:

   ``` Powershell
   Grant-CsTeamsIPPhonePolicy –Identity 'conf-adams@contoso.com' –PolicyName 'Meeting Sign In'
   ```

Dopo aver concesso il criterio all'account della risorsa sala riunioni, è necessario attendere la replica dell'assegnazione dei criteri. Dovrai anche disconnetterti dal dispositivo e accedere di nuovo.
