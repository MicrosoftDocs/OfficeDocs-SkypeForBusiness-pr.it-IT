---
title: Impostare l'interfaccia utente dei dispositivi Android di Microsoft Teams
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
appliesto:
- Microsoft Teams
ms.reviewer: ''
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Devices
description: Informazioni su come impostare l'interfaccia utente nei dispositivi Teams Android.
ms.openlocfilehash: 830609d1bf02c38a2301c0d5a1b9e62ac836c908
ms.sourcegitcommit: 75dfc3cd9b59282d68e35e4d7185da572eb3795c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2022
ms.locfileid: "67606835"
---
# <a name="set-microsoft-teams-android-devices-user-interface"></a>Impostare l'interfaccia utente dei dispositivi Android di Microsoft Teams

I dispositivi Android di Microsoft Teams possono visualizzare una specifica interfaccia utente in base al tipo di licenza assegnata all'account connesso. È possibile eseguire l'override di questo comportamento e controllare quale interfaccia viene visualizzata. Questo articolo descrive in dettaglio come viene scelta l'interfaccia utente predefinita e come è possibile modificare l'interfaccia usando i criteri di PowerShell.

Esistono tre tipi di interfacce utente nei dispositivi Teams Android:

1. Utente
2. Area comune
3. Riunione

Se si [assegna una licenza utente](/microsoftteams/user-access) a un account, ad esempio una licenza E3 o E5, il dispositivo Teams visualizzerà l'interfaccia utente finale predefinita, che è completamente in primo piano per la maggior parte degli scenari utente. Tuttavia, se un dispositivo esegue una funzione specifica, ad esempio un telefono ad area comune o una sala riunioni, esistono interfacce utente specifiche per questi utilizzi.

Le tre immagini seguenti mostrano come cambia l'interfaccia utente in base alla licenza assegnata all'account utente. 

## <a name="end-user-interface"></a>Interfaccia utente finale 

All'account utente è assegnata una licenza E5. Si tratta di una licenza utente, quindi il dispositivo mostra l'interfaccia utente finale predefinita:

:::image type="content" source="../media/teams-android-devices-usermode1.jpg" alt-text="Interfaccia in modalità utente.":::

## <a name="common-area-interface"></a>Interfaccia area comune

In questa immagine all'account utente è stata assegnata una [licenza common area phone](/microsoftteams/set-up-common-area-phones). I telefoni ad area comune vengono utilizzati principalmente per effettuare e ricevere chiamate telefoniche. Di conseguenza, la tastiera del telefono viene visualizzata sullo schermo:

:::image type="content" source="../media/teams-android-devices-cap1.jpg" alt-text="Interfaccia del telefono area comune.":::

## <a name="meeting-interface"></a>Interfaccia riunione

Questa immagine mostra un account utente con una [licenza Microsoft Teams Rooms](/MicrosoftTeams/rooms/rooms-licensing) assegnata. Teams Rooms licenze sono progettate per essere usate nelle sale riunioni o negli spazi condivisi, quindi l'interfaccia utente cambia per semplificare l'accesso a una riunione mostrando la visualizzazione Calendario:

:::image type="content" source="../media/teams-android-devices-meeting.jpg" alt-text="Interfaccia riunione.":::

> [!NOTE]
> La modifica dell'interfaccia utente non influisce sulla possibilità di utilizzare altre funzionalità concesse in licenza. Ad esempio, anche se la visualizzazione predefinita della licenza Gruppi di team è la visualizzazione calendario, è comunque possibile effettuare e ricevere telefonate PSTN (Public Switch Telephone Network) se l'account è configurato e concesso in licenza correttamente.

> [!IMPORTANT]
> Ci sono altri elementi dell'interfaccia che cambiano. Ad esempio, per impedire agli utenti finali di disconnettersi da un telefono dell'area comune o da un dispositivo della sala riunioni, l'opzione "Disconnetti" in questi dispositivi viene spostata in una parte del menu delle impostazioni che richiede autorizzazioni di amministratore per l'accesso.

## <a name="override-automatic-user-interface-detection"></a>Eseguire l'override del rilevamento automatico dell'interfaccia utente

In alcuni casi, è possibile scegliere di assegnare una licenza a un account che non corrisponde all'uso previsto. Ad esempio, è possibile assegnare una licenza utente a un account destinato ad accedere a Teams Rooms su Android. Per impostazione predefinita, viene visualizzata l'interfaccia utente finale invece dell'interfaccia della sala riunioni. Per ignorare l'interfaccia predefinita, creare un nuovo [criterio telefonico IP di Teams](/powershell/module/skype/new-csteamsipphonepolicy) e applicarlo a tale account.

> [!NOTE]
> La licenza assegnata all'account utente deve avere almeno gli stessi diritti di licenza dell'interfaccia utente desiderata. La licenza Common Area Phone consente solo l'interfaccia utente del telefono area comune. La licenza della sala riunioni consente le interfacce utente della sala riunioni e del telefono dell'area comune. Una licenza E3 o E5 supporta tutte le modalità di accesso.

Di seguito è riportato un esempio di come ignorare il rilevamento automatico delle licenze. In questo esempio si presuppone che a un account di risorse della sala riunioni denominato conf-adams@contoso.com sia stata assegnata una licenza E3. Quando l'account è connesso, si vuole che gli utenti vedano l'interfaccia utente della sala riunioni.

### <a name="create-a-new-policy-and-assign-to-user"></a>Creare un nuovo criterio e assegnarlo all'utente

1. Avviare una sessione di Windows PowerShell remota e connettersi a Microsoft Teams usando il cmdlet seguente:

    ``` Powershell
    Connect-MicrosoftTeams
    ```

2. Creare un nuovo criterio telefono IP di Teams e impostare la modalità di accesso su "MeetingSignIn":

   ``` Powershell
   New-CsTeamsIPPhonePolicy –Identity 'Meeting Sign in' –Description 'Meeting Sign In Phone Policy' -SignInMode 'MeetingSignIn'

   ```

3. È ora possibile assegnare questo nuovo criterio all'account delle risorse della sala riunioni:

   ``` Powershell
   Grant-CsTeamsIPPhonePolicy –Identity 'conf-adams@contoso.com' –PolicyName 'Meeting Sign In'
   ```

Dopo aver concesso il criterio all'account delle risorse della sala riunioni, è necessario attendere la replica dell'assegnazione dei criteri. Dovrai anche disconnetterti dal dispositivo ed eseguire di nuovo l'accesso.

## <a name="impact-on-microsoft-teams-admin-center"></a>Impatto sull'interfaccia di amministrazione di Microsoft Teams

L'interfaccia di amministrazione di Microsoft Teams consente di gestire i dispositivi di Microsoft Teams. Per altre informazioni sulla gestione dei dispositivi tramite l'interfaccia di amministrazione di Teams, vedere [Gestire i dispositivi in Microsoft Teams](device-management.md).


L'interfaccia di amministrazione di Teams offre la possibilità di gestire i telefoni di Teams. I telefoni sono filtrati in una delle tre schede in base alla loro funzione: telefoni utente, telefoni dell'area comune e telefono da conferenza. 

 :::image type="content" source="../media/teams-admin-center-phones-header.png" alt-text="Intestazione telefoni nell'interfaccia di amministrazione di Teams.":::

Come per il rilevamento dell'interfaccia utente, i telefoni di Teams sono categorizzati in base alla licenza assegnata all'account che accede al telefono. Ad esempio, se un account a cui è assegnata una licenza di area geografica comune accede a un telefono, il telefono verrà visualizzato sia nella sezione predefinita **Tutti i telefoni** che nella sezione **Telefoni dell'area comune** .

Se si vuole che un telefono venga visualizzato in una sezione diversa, è possibile assegnare una licenza diversa al telefono oppure creare e assegnare criteri per il telefono IP di Teams come [descritto in precedenza](#override-automatic-user-interface-detection).
