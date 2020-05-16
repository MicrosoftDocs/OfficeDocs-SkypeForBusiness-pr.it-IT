---
title: Creare un account risorse con l'interfaccia di amministrazione di Microsoft 365
description: Se si preferisce usare un'interfaccia utente grafica, è possibile creare un account delle risorse per le sale di Microsoft teams e le barre di collaborazione per Microsoft teams con Microsoft 365 Admin Center.
ms.reviewer: payurevi
manager: serdars
audience: ITPro
keywords: creare un account di dispositivo, Microsoft 365 UI, Microsoft 365 Admin Center
ms.sitesec: library
ms.service: msteams
author: flinchbot
ms.author: mitressl
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: 1137f462b9c21455f3a65a87075fd653b5c081b9
ms.sourcegitcommit: f0ccafb7e9c2d382ab4545e085657e8129024f1d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/16/2020
ms.locfileid: "44268036"
---
# <a name="create-a-microsoft-365-resource-account-using-the-microsoft-365-admin-center"></a>Creare un account delle risorse di Microsoft 365 tramite l'interfaccia di amministrazione di Microsoft 365

Gli account delle risorse di Microsoft 365 sono account di cassette postali e team dedicati a risorse specifiche, ad esempio una sala, un proiettore e così via. Questi account delle risorse possono rispondere automaticamente agli inviti alle riunioni usando le regole definite durante la creazione. Ad esempio, se si ha una risorsa comune, come una sala riunioni, è possibile configurare un account delle risorse per la sala riunioni che accetterà automaticamente o rifiuterà gli inviti alle riunioni a seconda della disponibilità del calendario.

<!-- The steps in this article show you how to set up a resource account using the Microsoft 365 admin center. If you'd rather use PowerShell to create resource accounts, [Create a resource account using the PowerShell](resource-account-ps.md). -->

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

## <a name="licensing"></a>Licenze

Prima di creare un account delle risorse di Microsoft 365, verificare il tipo di licenza necessario. Se si usa solo un account delle risorse per prenotare una risorsa, ovvero invitare la risorsa alla riunione e accettare o rifiutare automaticamente l'invito, non è necessario assegnare una licenza a un account delle risorse. È necessario assegnare una licenza per l'account delle risorse nelle situazioni seguenti:

- **Riunione teams** Se si vuole che la risorsa, ad esempio una console Microsoft teams rooms, una barra di collaborazione e così via, partecipi a una riunione di teams in modo che i partecipanti possano usarla per presentare video e audio, è necessaria una licenza per la sala riunioni. 
- **Chiamate PSTN** Se si vuole che la risorsa effettui o riceva chiamate da o verso un numero di telefono esterno (chiamato rete telefonica pubblica o chiamata PSTN), è necessario un sistema telefonico Microsoft 365 o una licenza vocale di Microsoft 365 business.

Per altre informazioni su sala riunioni, sistema telefonico e licenze vocali aziendali, vedere [licenze per i componenti aggiuntivi Microsoft teams](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md)

## <a name="create-a-resource-account-in-the-microsoft-365-admin-center"></a><a href="" id="create-device-acct-m365-admin-ctr"></a>Creare un account risorse nell'interfaccia di amministrazione di Microsoft 365

1. Accedere a Microsoft 365 visitandohttps://admin.microsoft.com
2. Fornisci le credenziali di amministratore per il tenant di Microsoft 365. In questo modo è possibile usare l'interfaccia di amministrazione di Microsoft 365.

:::image type="content" source="../media/collaboration-bar-m365-admin-center.png" alt-text="Interfaccia di amministrazione di Microsoft 365":::
3. Nell'interfaccia di amministrazione passare a **risorse** nel riquadro sinistro (potrebbe essere necessario selezionare **Mostra tutto** ) e quindi selezionare **sale & attrezzature**.

:::image type="content" source="../media/collaboration-bar-m365-resources-rooms.png" alt-text="Interfaccia di amministrazione di Microsoft 365-risorse":::
4. Selezionare **Aggiungi una cassetta postale delle risorse** per creare un nuovo account di chat room. Immettere un nome visualizzato e un indirizzo di posta elettronica per l'account, fare clic su **Aggiungi**e quindi selezionare **Chiudi**. È consigliabile standardizzare una convenzione di denominazione per tutti gli account delle risorse.

> [!NOTE]
> Per impostazione predefinita, gli account delle risorse sono configurati con le impostazioni seguenti. Se si desidera modificarle, selezionare **Imposta opzioni di pianificazione** prima di selezionare **Chiudi**. Se si desidera modificarle in un secondo momento, passare a **risorse**  >  **sale & attrezzature**, selezionare l'account delle risorse e quindi selezionare **modifica** in **Opzioni di prenotazione**.
>
> - Consenti riunioni ripetute
> - Rifiutare automaticamente le riunioni al di fuori dei limiti seguenti
>   - Finestra di prenotazione (giorni): 180
>   - Durata massima (ore): 24
> - Accettare automaticamente le convocazioni di riunione

:::image type="content" source="../media/collaboration-bars-admin-resources.png" alt-text="Interfaccia di amministrazione di Microsoft 365-aggiungere risorse":::
5. Passare alla sezione **utenti** nell'interfaccia di amministrazione e, nell'elenco **utenti attivi** , verrà visualizzata la chat room appena creata.

:::image type="content" source="../media/collaboration-bars-M3565-admin-active-users.png" alt-text="Interfaccia di amministrazione di Microsoft 365-vedere utenti attivi":::
6. Selezionare il nome della chat room e il riquadro delle proprietà dell'account verrà visualizzato a destra.

:::image type="content" source="../media/collaboration-bar-m365-admin-center-active-user-settings.png" alt-text="Interfaccia di amministrazione di Microsoft 365-proprietà degli utenti":::
7. Ora è necessario assegnare una password all'account delle risorse. Nel pannello è possibile visualizzare le proprietà dell'account e diverse azioni facoltative. Selezionare l'icona **Reimposta chiave password** sotto il nome utente per cambiare la password. Deseleziona **Richiedi all'utente di cambiare la password al primo accesso**. Non è possibile cambiare la password tramite il processo di accesso al dispositivo. Selezionare **Reimposta**.

:::image type="content" source="../media/collaboration-bar-m365-admin-center-active-user-password.png" alt-text="Interfaccia di amministrazione di Microsoft 365-reimpostare la password":::
8. Nella sezione **licenze e app** impostare **Seleziona posizione** nel paese o nell'area geografica in cui verrà installato il dispositivo. Scorrere verso il basso e selezionare la casella accanto alla licenza da assegnare, ad esempio sala riunioni, quindi fare clic su **Salva modifiche**. La licenza può variare a seconda dell'organizzazione.

:::image type="content" source="../media/collaboration-bar-m365-admin-center-active-user-assign-license.png" alt-text="Interfaccia di amministrazione di Microsoft 365-assegnare una licenza":::
