---
title: Creare un account delle risorse con l'interfaccia di amministrazione di Microsoft 365
description: Se si preferisce usare un'interfaccia utente grafica, è possibile creare un account delle risorse per le sale e le barre di collaborazione di Microsoft Teams per Microsoft Teams usando l'interfaccia di amministrazione di Microsoft 365.
ms.reviewer: payurevi
manager: serdars
audience: ITPro
keywords: creare un account dispositivo, interfaccia utente di Microsoft 365, interfaccia di amministrazione di Microsoft 365
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
# <a name="create-a-microsoft-365-resource-account-using-the-microsoft-365-admin-center"></a>Creare un account delle risorse di Microsoft 365 con l'interfaccia di amministrazione di Microsoft 365

Gli account delle risorse di Microsoft 365 sono account delle cassette postali e di Teams dedicati a risorse specifiche, ad esempio una sala, un proiettore e così via. Questi account delle risorse possono rispondere automaticamente agli inviti alle riunioni usando le regole definite dall'utente quando vengono create. Ad esempio, se si ha una risorsa comune come una sala riunioni, è possibile configurare un account della risorsa per tale sala riunioni che accetterà o rifiutarà automaticamente gli inviti alle riunioni in base alla disponibilità nel calendario.

<!-- The steps in this article show you how to set up a resource account using the Microsoft 365 admin center. If you'd rather use PowerShell to create resource accounts, [Create a resource account using the PowerShell](resource-account-ps.md). -->

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

## <a name="licensing"></a>Licenze

Prima di creare un account delle risorse di Microsoft 365, verificare il tipo di licenza necessario. Se si userà un account delle risorse solo per prenotare una risorsa, ovvero per invitare la risorsa alla riunione, in modo che accetti o rifiuti automaticamente l'invito, non è necessario assegnare una licenza a un account delle risorse. È necessario assegnare una licenza all'account delle risorse nelle situazioni seguenti:

- **Riunione di Teams** Se si vuole che la risorsa (ad esempio una console Microsoft Teams Rooms, la barra di collaborazione e così via) si unirà a una riunione di Teams in modo che i partecipanti possano usarla per presentare video e audio attraverso di essa, è necessaria una licenza per la sala riunioni. 
- **Chiamate PSTN** Se si vuole che la risorsa riceva chiamate verso o da numeri di telefono esterni (chiamate PSTN o Public Switched Telephone Network), è necessaria una licenza Sistema telefonico Microsoft 365 o Microsoft 365 Business Voice.

Per altre informazioni sulle licenze Sala riunioni, Sistema telefonico e Voce aziendale, vedere licenze [per i componenti](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md) aggiuntivi Microsoft Teams

## <a name="create-a-resource-account-in-the-microsoft-365-admin-center"></a><a href="" id="create-device-acct-m365-admin-ctr"></a>Creare un account delle risorse nell'interfaccia di amministrazione di Microsoft 365

1. Accedi a Microsoft 365 visitando https://admin.microsoft.com
2. Fornire le credenziali di amministratore per il tenant di Microsoft 365. Verrà visualizzato l'interfaccia di amministrazione di Microsoft 365.

:::image type="content" source="../media/collaboration-bar-m365-admin-center.png" alt-text="Interfaccia di amministrazione di Microsoft 365":::
3. Nell'interfaccia di amministrazione  passare a Risorse nel riquadro  sinistro (potrebbe essere necessario selezionare Mostra tutto) e quindi selezionare Sale & **attrezzatura.**

:::image type="content" source="../media/collaboration-bar-m365-resources-rooms.png" alt-text="Interfaccia di amministrazione di Microsoft 365 - Risorse":::
4. Selezionare **Aggiungi cassetta postale delle risorse** per creare un nuovo account della chat room. Immettere un nome visualizzato e un indirizzo di posta elettronica per l'account, selezionare **Aggiungi** e **quindi** Chiudi. È consigliabile standardizzare una convenzione di denominazione per tutti gli account delle risorse.

> [!NOTE]
> Per impostazione predefinita, gli account delle risorse sono impostati con le impostazioni seguenti. Per modificarle, selezionare Imposta **opzioni di pianificazione** prima di scegliere **Chiudi.** Se si vuole modificarle in un secondo momento, passare a Sale risorse & attrezzatura, selezionare l'account della risorsa e quindi selezionare Modifica in  >  Opzioni **di prenotazione.** 
>
> - Consentire riunioni ricorrenti
> - Rifiutare automaticamente le riunioni al di fuori dei limiti seguenti
>   - Finestra di prenotazione (giorni): 180
>   - Durata massima (ore): 24
> - Accettare automaticamente le convocazioni riunione

:::image type="content" source="../media/collaboration-bars-admin-resources.png" alt-text="Interfaccia di amministrazione di Microsoft 365 - Aggiungere risorse":::
5. Passare alla **sezione Utenti** nell'interfaccia  di amministrazione e nell'elenco Utenti attivi verrà visualizzata la chat room appena creata.

:::image type="content" source="../media/collaboration-bars-M3565-admin-active-users.png" alt-text="Interfaccia di amministrazione di Microsoft 365 - Vedere gli utenti attivi":::
6. Selezionare il nome della chat room per visualizzare il riquadro delle proprietà di un account sulla destra.

:::image type="content" source="../media/collaboration-bar-m365-admin-center-active-user-settings.png" alt-text="Interfaccia di amministrazione di Microsoft 365 - Proprietà utente":::
7. Ora è necessario assegnare una password all'account delle risorse. Nel riquadro sono disponibili le proprietà dell'account e diverse azioni facoltative. Selezionare **l'icona di reimpostazione** della password sotto il nome utente per cambiare la password. Deselezionare **Richiedi a questo utente di cambiare la password al primo accesso.** Non è possibile cambiare la password tramite la procedura di accesso del dispositivo. Selezionare **Reimposta.**

:::image type="content" source="../media/collaboration-bar-m365-admin-center-active-user-password.png" alt-text="Interfaccia di amministrazione di Microsoft 365 - Reimposta password":::
8. Nella sezione **Licenze e app** impostare Seleziona la **posizione** in base al paese o all'area geografica in cui verrà installato il dispositivo. Scorrere verso il basso e selezionare la casella accanto alla licenza da assegnare, ad esempio Sala riunioni, e quindi **selezionare Salva modifiche.** La licenza può variare a seconda dell'organizzazione.

:::image type="content" source="../media/collaboration-bar-m365-admin-center-active-user-assign-license.png" alt-text="Interfaccia di amministrazione di Microsoft 365 - Assegna licenza":::
