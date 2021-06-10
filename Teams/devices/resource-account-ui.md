---
title: Creare un account della risorsa usando l'interfaccia Microsoft 365 di amministrazione
description: Se si preferisce usare un'interfaccia utente grafica, è possibile creare un account delle risorse per il Microsoft Teams Rooms e le barre di collaborazione per Microsoft Teams usando l'interfaccia di amministrazione di Microsoft 365.
ms.reviewer: payurevi
manager: serdars
audience: ITPro
keywords: creare un account del dispositivo, Microsoft 365'interfaccia utente e Microsoft 365 di amministrazione
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
# <a name="create-a-microsoft-365-resource-account-using-the-microsoft-365-admin-center"></a>Creare un account Microsoft 365 con l'interfaccia Microsoft 365 di amministrazione

Microsoft 365 account delle risorse sono account Teams cassette postali e account dedicati a risorse specifiche, ad esempio una sala, un proiettore e così via. Questi account delle risorse possono rispondere automaticamente agli inviti alle riunioni usando le regole definite al momento della creazione. Ad esempio, se si ha una risorsa comune, ad esempio una sala riunioni, è possibile configurare un account della risorsa per tale sala riunioni che accetti o rifiuti automaticamente gli inviti alle riunioni a seconda della disponibilità del calendario.

<!-- The steps in this article show you how to set up a resource account using the Microsoft 365 admin center. If you'd rather use PowerShell to create resource accounts, [Create a resource account using the PowerShell](resource-account-ps.md). -->

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

## <a name="licensing"></a>Licenze

Prima di creare un account Microsoft 365 risorsa, verificare il tipo di licenza necessario. Se si userà un account della risorsa solo per prenotare una risorsa, ovvero invitare la risorsa alla riunione e fare in modo che accetti o rifiuti automaticamente l'invito, non è necessario assegnare una licenza a un account della risorsa. È necessario assegnare una licenza all'account della risorsa nelle situazioni seguenti:

- **Teams riunione** Se si vuole che la risorsa, ad esempio una console di Microsoft Teams Rooms, una barra di collaborazione e così via, si unirà a una riunione di Teams in modo che i partecipanti possano usarla per presentare video e audio attraverso di essa, è necessaria una licenza Sala riunioni. 
- **Chiamate PSTN** Se si vuole che la risorsa eseere o riceva chiamate da o verso un numero di telefono esterno (chiamata rete telefonica a commutazione pubblica o chiamata PSTN), è necessaria una licenza Microsoft 365 Sistema telefonico o Microsoft 365 Business Voice telefonica.

Per altre informazioni sulle licenze Sala riunioni, Sistema telefonico e Business Voice, vedere licenze per [Microsoft Teams componenti aggiuntivi](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md)

## <a name="create-a-resource-account-in-the-microsoft-365-admin-center"></a><a href="" id="create-device-acct-m365-admin-ctr"></a>Creare un account della risorsa nell'interfaccia Microsoft 365 di amministrazione

1. Accedi a Microsoft 365 visitandohttps://admin.microsoft.com
2. Specificare le credenziali di amministratore per il tenant Microsoft 365 tenant. Verrà visualizzato l'interfaccia Microsoft 365 di amministrazione.

:::image type="content" source="../media/collaboration-bar-m365-admin-center.png" alt-text="Microsoft 365 di amministrazione":::
3. Nell'interfaccia di amministrazione  passare a Risorse nel riquadro  sinistro (potrebbe essere necessario selezionare Prima Mostra tutto) e quindi selezionare & **apparecchiature.**

:::image type="content" source="../media/collaboration-bar-m365-resources-rooms.png" alt-text="Microsoft 365 di amministrazione - Risorse":::
4. Selezionare **Aggiungi una cassetta postale della risorsa** per creare un nuovo account della chat room. Immettere un nome visualizzato e un indirizzo di posta elettronica per l'account, selezionare **Aggiungi** e quindi selezionare **Chiudi.** È consigliabile standardizzare una convenzione di denominazione per tutti gli account delle risorse.

> [!NOTE]
> Per impostazione predefinita, gli account delle risorse sono impostati con le impostazioni seguenti. Per modificarle, selezionare Imposta opzioni **di pianificazione** prima di selezionare **Chiudi.** Per modificarle in un secondo momento, passare a Sale risorse & attrezzature, selezionare l'account della risorsa e quindi selezionare Modifica  >  in Opzioni **di prenotazione.** 
>
> - Consentire riunioni ripetute
> - Rifiutare automaticamente le riunioni al di fuori dei limiti seguenti
>   - Finestra di prenotazione (giorni): 180
>   - Durata massima (ore): 24
> - Accettare automaticamente convocazioni di riunione

:::image type="content" source="../media/collaboration-bars-admin-resources.png" alt-text="Microsoft 365 di amministrazione - Aggiungere risorse":::
5. Passare alla **sezione Utenti** nell'interfaccia di amministrazione e, nell'elenco Utenti attivi, verrà visualizzata la chat room appena creata. 

:::image type="content" source="../media/collaboration-bars-M3565-admin-active-users.png" alt-text="Microsoft 365 di amministrazione - Vedere gli utenti attivi":::
6. Selezionare il nome della chat room e a destra verrà visualizzato il riquadro delle proprietà dell'account.

:::image type="content" source="../media/collaboration-bar-m365-admin-center-active-user-settings.png" alt-text="Microsoft 365 di amministrazione - Proprietà utente":::
7. Ora è necessario assegnare una password all'account della risorsa. Nel riquadro sono disponibili le proprietà dell'account e diverse azioni facoltative. Selezionare **l'icona Reimposta chiave password** sotto il nome utente per cambiare la password. Deselezionare **Richiedi a questo utente di cambiare la password al primo accesso.** Non è possibile cambiare la password tramite il processo di accesso del dispositivo. Selezionare **Reimposta**.

:::image type="content" source="../media/collaboration-bar-m365-admin-center-active-user-password.png" alt-text="Microsoft 365 di amministrazione - Reimposta password":::
8. Nella sezione **Licenze e app** impostare Seleziona **posizione** sul paese o sull'area geografica in cui verrà installato il dispositivo. Scorrere verso il basso e selezionare la casella accanto alla licenza da assegnare, ad esempio Sala riunioni, e quindi selezionare **Salva modifiche**. La licenza può variare a seconda dell'organizzazione.

:::image type="content" source="../media/collaboration-bar-m365-admin-center-active-user-assign-license.png" alt-text="Microsoft 365 di amministrazione - Assegnare una licenza":::
