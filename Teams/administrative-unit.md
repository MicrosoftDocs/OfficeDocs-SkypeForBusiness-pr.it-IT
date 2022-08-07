---
title: Gestire i dispositivi con unità amministrative
author: CarolynRowe
ms.author: crowe
ms.reviewer: prasad.ghlove
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Informazioni su come usare le unità amministrative in Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Devices
appliesto:
- Microsoft Teams
ms.openlocfilehash: b1ccc079617a1ae58b3881da8ae48c8a993d5863
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2022
ms.locfileid: "67269471"
---
# <a name="manage-devices-in-the-teams-admin-center-with-administrative-units"></a>Gestire i dispositivi nell'interfaccia di amministrazione di Teams con unità amministrative

Le unità amministrative nell'interfaccia di amministrazione di Teams forniscono un accesso dettagliato basato sui ruoli per la gestione dei dispositivi Teams. Le unità amministrative concedono l'accesso di amministratore di Teams a risorse specifiche, ma limitano l'accesso di tale amministratore ad altre risorse. Questa funzionalità è particolarmente utile se si hanno amministratori di Teams locali in paesi o aree geografiche diversi.

Ad esempio, Contoso ha operazioni in tutto il mondo. Alice è un amministratore IT globale con sede a Londra, mentre Prashant è un amministratore IT locale con sede a Bangalore, India. Oggi, quando Prashant accede all'interfaccia di amministrazione di Teams come amministratore dei dispositivi, può vedere i dispositivi Teams in tutto il mondo. Alice vuole limitare l'accesso di Prashant ai dispositivi Teams solo in Bangalore. Le unità amministrative le permettono di farlo. Per altre informazioni, vedere [Unità amministrative in Azure Active Directory](/azure/active-directory/roles/administrative-units).

> [!NOTE]
> Le unità amministrative sono attualmente disponibili nell'interfaccia di amministrazione di Teams solo per il ruolo di amministratore dei dispositivi Teams.

## <a name="add-administrative-units"></a>Aggiungere unità amministrative

È necessario essere un amministratore globale per aggiungere unità amministrative. Per informazioni sulla procedura, vedere [Aggiungere un'unità amministrativa](/azure/active-directory/roles/admin-units-manage#add-an-administrative-unit).

## <a name="assign-admins-to-administrative-units"></a>Assegnare amministratori alle unità amministrative

È anche necessario essere amministratore globale per assegnare unità amministrative. È possibile assegnare unità amministrative usando portale di Azure, PowerShell o l'API Graph Microsoft. Per altre informazioni, vedere [Assegnare ruoli di Azure AD con ambito di unità di amministrazione](/azure/active-directory/roles/admin-units-assign-roles).

## <a name="select-administrative-units"></a>Selezionare le unità amministrative

Se sei un amministratore dei dispositivi di Teams, dopo che un amministratore globale ti ha assegnato a un'unità amministrativa, puoi accedere all'interfaccia di amministrazione di Teams per gestire i dispositivi. Se si è assegnati a una sola unità amministrativa, verranno visualizzati solo i dispositivi assegnati a tale unità amministrativa. Se si è assegnati a più unità amministrative, è possibile passare da un'unità amministrativa all'altra senza disconnettersi dall'interfaccia di amministrazione di Teams. 

1. Accedere [all'interfaccia di amministrazione di Teams](https://go.microsoft.com/fwlink/p/?linkid=2024339).

2. Nella finestra di dialogo **Unità amministrative** eseguire una di queste operazioni:
    - Selezionare l'unità amministrativa da gestire oppure 
    - Selezionare **Tutti i dispositivi** se si dispone dell'autorizzazione per gestire tutti i dispositivi per l'organizzazione.

3. Selezionare **Salva**.

## <a name="switch-administrative-units"></a>Cambiare unità amministrative

Gli amministratori di dispositivi Teams possono passare da un'unità amministrativa all'altra se si è connessi all'interfaccia di amministrazione di Teams. Per passare a un'unità amministrativa diversa:

1. Accedere [all'interfaccia di amministrazione di Teams](https://go.microsoft.com/fwlink/p/?linkid=2024339).

2. Nella barra di spostamento sinistra selezionare **Dispositivi di Teams**.

3. Nel riquadro destro, in alto a sinistra, selezionare l'unità di amministrazione visualizzata.

4. Nella finestra di dialogo **Unità amministrative** eseguire una di queste operazioni:
    - Selezionare l'unità amministrativa da gestire oppure 
    - Selezionare **Tutti i dispositivi** se si dispone dell'autorizzazione per gestire tutti i dispositivi per l'organizzazione.

5. Selezionare **Salva**.

## <a name="related-topics"></a>Argomenti correlati

- [Aggiungere utenti o gruppi a un'unità amministrativa](/azure/active-directory/roles/admin-units-members-add)
