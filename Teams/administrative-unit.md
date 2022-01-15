---
title: Gestire i dispositivi con unità amministrative
author: mahoffman
ms.author: v-mahoffman
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
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6a4130cbd9493a37d84f0b15160adcaeb03c9edd
ms.sourcegitcommit: 8f999bd2e20f177c6c6d8b174ededbff43ff5076
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2022
ms.locfileid: "62056179"
---
# <a name="manage-devices-in-the-teams-admin-center-with-administrative-units"></a>Gestire i dispositivi nell'Teams di amministrazione con unità amministrative

Le unità amministrative nell'Teams di amministrazione forniscono un accesso dettagliato e basato sui ruoli per la gestione Teams dispositivi. Le unità amministrative concedono Teams'accesso a risorse specifiche, ma limitano l'accesso di tale amministratore ad altre risorse. Questa opzione è particolarmente utile se si hanno amministratori locali Teams in diversi paesi o aree geografiche.

Ad esempio, Contoso ha operazioni in tutto il mondo. Alice è un amministratore IT globale con sede a Londra, mentre Prashant è un amministratore IT locale con sede a Bangalore, India. Oggi, quando Prashant accede all'interfaccia Teams di amministrazione come amministratore di dispositivi, può vedere Teams dispositivi in tutto il mondo. Alice vuole limitare l'accesso di Prashant ai Teams solo a Bangalore. Le unità amministrative le consentono di eseguire questa operazione. Per altre informazioni, vedere [Unità amministrative in Azure Active Directory](/azure/active-directory/roles/administrative-units).

> [!NOTE]
> Le unità amministrative sono attualmente disponibili nell'interfaccia di amministrazione Teams solo per il ruolo di amministratore Teams dispositivi mobili.

## <a name="add-administrative-units"></a>Aggiungere unità amministrative

Per aggiungere unità amministrative, è necessario essere un amministratore globale. Per informazioni, vedere [Aggiungere un'unità amministrativa.](/azure/active-directory/roles/admin-units-manage#add-an-administrative-unit)

## <a name="assign-admins-to-administrative-units"></a>Assegnare amministratori alle unità amministrative

È anche necessario essere amministratori globali per assegnare unità amministrative. È possibile assegnare unità amministrative usando il portale di Azure, PowerShell o l'API Graph Microsoft. Per altre informazioni, vedere [Assegnare ruoli Azure AD con ambito di unità amministrative.](/azure/active-directory/roles/admin-units-assign-roles)

## <a name="select-administrative-units"></a>Selezionare le unità amministrative

Gli amministratori dei dispositivi Teams, dopo che un amministratore globale ti ha assegnato a un'unità amministrativa, puoi accedere all'interfaccia di amministrazione di Teams per gestire i dispositivi. Se si è assegnati a una sola unità amministrativa, verranno visualizzati solo i dispositivi assegnati a tale unità amministrativa. Se si è assegnati a più unità amministrative, è possibile passare da quelle unità amministrative senza uscire dall'interfaccia di amministrazione Teams. 

1. Accedere all'interfaccia [Teams di amministrazione .](https://go.microsoft.com/fwlink/p/?linkid=2024339)

2. Nella finestra **di dialogo Unità amministrative** eseguire una delle operazioni seguenti:
    - Selezionare l'unità amministrativa da gestire oppure 
    - Selezionare **Tutti i dispositivi** se si ha l'autorizzazione per gestire tutti i dispositivi per l'organizzazione.

3. Selezionare **Salva**.

## <a name="switch-administrative-units"></a>Cambiare unità amministrative

Se si è un amministratore Teams dispositivi mobili, è possibile passare da un'unità amministrativa all'altro se è stato eseguito l'accesso all'interfaccia di amministrazione Teams di amministrazione. Per passare a un'unità amministrativa diversa:

1. Accedere all'interfaccia [Teams di amministrazione .](https://go.microsoft.com/fwlink/p/?linkid=2024339)

2. Nel riquadro di spostamento sinistro selezionare **Teams dispositivi**.

3. Nel riquadro destro, in alto a sinistra, selezionare l'unità amministrativa visualizzata.

4. Nella finestra **di dialogo Unità amministrative** eseguire una delle operazioni seguenti:
    - Selezionare l'unità amministrativa da gestire oppure 
    - Selezionare **Tutti i dispositivi** se si ha l'autorizzazione per gestire tutti i dispositivi per l'organizzazione.

5. Selezionare **Salva**.
