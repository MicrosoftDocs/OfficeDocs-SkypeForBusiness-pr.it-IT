---
title: Impostare l Microsoft Teams'interfaccia utente dei dispositivi Android
ms.author: mitressl
author: flinchbot
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
description: Scopri come impostare l'interfaccia utente nei Teams Android.
ms.openlocfilehash: cf0c60fa5073ee2a3915f2450900865bc058e295
ms.sourcegitcommit: a969502c0a5237caf041d7726f4f1edefdd75b44
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2022
ms.locfileid: "61767429"
---
# <a name="set-microsoft-teams-android-devices-user-interface"></a>Impostare l Microsoft Teams'interfaccia utente dei dispositivi Android

Microsoft Teams dispositivi Android possono visualizzare un'interfaccia utente specifica in base al tipo di licenza assegnata all'account di accesso. È possibile eseguire l'override di questo comportamento e controllare l'interfaccia visualizzata. Questo articolo descrive in dettaglio come viene scelta l'interfaccia utente predefinita e come è possibile modificare l'interfaccia usando un criterio di PowerShell.

Esistono tre tipi di interfacce utente nei Teams Android:

1. Utente
2. Area comune
3. Riunione

Se si assegna una licenza utente [a](/microsoftteams/user-access) un account, ad esempio una licenza E3 o E5, il dispositivo Teams visualizza l'interfaccia utente finale predefinita, completamente in primo piano per la maggior parte degli scenari utente. Tuttavia, se un dispositivo esegue una funzione specifica, ad esempio un telefono di area comune o una sala riunioni, esistono interfacce utente specifiche per questi utilizzi.

Le tre immagini seguenti mostrano come cambia l'interfaccia utente in base alla licenza assegnata all'account utente. Nella prima immagine all'account utente viene assegnata una licenza E5. Si tratta di una licenza utente, quindi il dispositivo mostra l'interfaccia utente finale predefinita:

:::image type="content" source="../media/teams-android-devices-usermode1.jpg" alt-text="Interfaccia in modalità utente.":::

In questa immagine all'account utente è stata assegnata una [licenza per il telefono dell'area comune.](/microsoftteams/set-up-common-area-phones) I telefoni dell'area comune vengono usati principalmente per effettuare e ricevere chiamate telefoniche. Di conseguenza, la tastiera del telefono viene visualizzata sullo schermo:

:::image type="content" source="../media/teams-android-devices-cap1.jpg" alt-text="Interfaccia del telefono dell'area comune.":::

Infine, questa immagine mostra un account utente con una licenza [Microsoft Teams Rooms Standard assegnata.](/MicrosoftTeams/rooms/rooms-licensing) Teams Rooms licenze sono destinate a essere usate nelle sale riunioni o negli spazi condivisi, quindi l'interfaccia utente cambia per semplificare la partecipazione a una riunione mostrando la visualizzazione calendario:

:::image type="content" source="../media/teams-android-devices-meeting.jpg" alt-text="Interfaccia riunione.":::

> [!NOTE]
> La modifica dell'interfaccia utente non influisce sulla possibilità di usare altre funzionalità con licenza. Ad esempio, anche se la visualizzazione predefinita della licenza Team Rooms è la visualizzazione calendario, è comunque possibile effettuare e ricevere chiamate PSTN (Public Switch Telephone Network) se l'account è correttamente concesso in licenza e configurato.

> [!IMPORTANT]
> Ci sono altri elementi dell'interfaccia che cambiano. Ad esempio, per impedire agli utenti finali di disconnettersi da un telefono dell'area comune o da un dispositivo della sala riunioni, l'opzione "Disconnetta" in questi dispositivi viene spostata in una parte del menu delle impostazioni che richiede le autorizzazioni di amministratore per l'accesso.

## <a name="override-automatic-user-interface-detection"></a>Ignorare il rilevamento automatico dell'interfaccia utente

In alcuni casi, è possibile scegliere di assegnare una licenza a un account che non corrisponde all'uso previsto. Ad esempio, è possibile assegnare una licenza utente a un account destinato ad accedere a Teams Rooms su Android. Per impostazione predefinita, viene visualizzata l'interfaccia utente finale invece dell'interfaccia della sala riunioni. Per ignorare l'interfaccia predefinita, creare un nuovo criterio di Teams [ip Telefono](/powershell/module/skype/new-csteamsipphonepolicy?view=skype-ps) e applicarlo a tale account.

> [!NOTE]
> La licenza assegnata all'account utente deve avere almeno gli stessi diritti di licenza dell'interfaccia utente desiderata. La licenza Telefono area comune consente solo l'interfaccia utente del telefono area comune. La licenza della sala riunioni consente di utilizzare le interfacce utente della sala riunioni e del telefono dell'area comune. Una licenza E3 o E5 supporta tutte le modalità di accesso.

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

## <a name="impact-on-microsoft-teams-admin-center"></a>Impatto sull'Microsoft Teams di amministrazione

Microsoft Teams'interfaccia di amministrazione consente di gestire Microsoft Teams dispositivi. Per altre informazioni sulla gestione dei dispositivi con Teams di amministrazione, vedere [Gestire i dispositivi in Microsoft Teams](device-management.md).


Teams'interfaccia di amministrazione offre la possibilità di gestire Teams telefoni. I telefoni vengono filtrati in una delle tre schede in base alla loro funzione: telefoni utente, telefoni dell'area comune e telefono conferenza. 

 :::image type="content" source="../media/teams-admin-center-phones-header.png" alt-text="Intestazione Telefoni nell Teams di amministrazione.":::

Come per il rilevamento dell'interfaccia utente, Teams telefoni sono categorizzati in base alla licenza assegnata all'account che accede al telefono. Ad esempio, se un account a cui è assegnata una licenza per il telefono dell'area comune accede a un telefono, il telefono verrà visualizzato sia nella sezione predefinita Tutti i telefoni che nella sezione Telefoni dell'area comune.  

Se si vuole che un telefono venga visualizzato in una sezione diversa, è possibile assegnare una licenza diversa al telefono oppure creare e assegnare un criterio di Teams ip Telefono come descritto [sopra.](#override-automatic-user-interface-detection)
