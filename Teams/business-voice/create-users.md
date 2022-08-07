---
title: Creare utenti di Microsoft 365, aggiungere Teams Phone con licenze bundle piano per chiamate e assegnare numeri di telefono
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
description: Informazioni su come creare e assegnare in licenza agli utenti il sistema telefonico Teams con piano per chiamate e assegnare loro numeri di telefono.
appliesto:
- Microsoft Teams
ms.collection:
- M365-voice
ms.openlocfilehash: ac665f46c7be619d26b0c6da371ba57e554a07ee
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2022
ms.locfileid: "67272001"
---
# <a name="create-and-license-teams-phone-system-with-calling-plan-bundle-users-and-assign-them-phone-numbers"></a>Creare e assegnare in licenza il sistema telefonico Teams con il piano per chiamate raggruppare gli utenti e assegnargli numeri di telefono

Per usare l'aggregazione Sistema telefonico teams con piano per chiamate, è necessario un account Microsoft 365 con licenze di Teams Phone con bundle del piano per chiamate. Quando hai un account e licenze, puoi iniziare ad assegnare numeri di telefono.

## <a name="create-and-license-users"></a>Creare utenti e assegnare licenze

Seguire i passaggi in [Aggiungere utenti singolarmente o in blocco ](/microsoft-365/admin/add-users/add-users) e [Assegnare licenze agli utenti](/microsoft-365/admin/manage/assign-licenses-to-users).

> [!NOTE]
> Nel riquadro **Assegna licenze di prodotto** , seleziona **Teams Phone with Calling Plan**.

## <a name="assign-phone-numbers-to-users"></a>Assegnare numeri di telefono agli utenti

Dopo aver creato gli utenti e assegnato Teams Phone con licenza bundle piano per chiamate, è possibile assegnare loro numeri di telefono. È necessario un numero di telefono non assegnato per ogni utente che deve effettuare o ricevere chiamate da numeri di telefono esterni. Se non si hanno numeri di telefono non assegnati sufficienti, vedere [Ottenere altri numeri di telefono](#get-more-phone-numbers) più avanti in questo articolo.

1. Passare all'[interfaccia di amministrazione di Teams](https://admin.teams.microsoft.com).
2. Immettere un nome e una descrizione per la richiesta di un numero di telefono.
3. Selezionare **Vocale** > **Numeri telefonici**.
4. Selezionare un numero di telefono che si vuole assegnare a un utente e quindi **Modifica**.
5. Nel riquadro **Modifica** immettere il nome dell'utente a cui si vuole assegnare il numero in **Assegnato a**. Selezionare quindi **Assegna**.
6. In **Posizione di emergenza** immettere il luogo in cui si trova l'utente e quindi selezionare **Applica**

## <a name="get-more-phone-numbers"></a>Ottenere altri numeri di telefono

Se non si hanno abbastanza numeri di telefono da assegnare ai nuovi utenti, è possibile ottenerne altri. Potrebbe essere necessario attendere fino a 24 ore prima che i numeri siano resi disponibili.

1. Passare all'[interfaccia di amministrazione di Teams](https://admin.teams.microsoft.com).
2. Immettere un nome e una descrizione per la richiesta di un numero di telefono.
3. Selezionare **Vocale** > **Numeri di telefono** > **Aggiungi**.
4. Selezionare il Paese o l'area geografica per il numero di telefono.
5. In **Tipo di numero** selezionare **Utente (abbonato)**.
6. In **Posizione** cercare la posizione dell'utente e selezionarla. È anche possibile scegliere **Aggiungi una posizione**.
7. Scegliere un prefisso, immettere il numero di numeri di telefono necessari e quindi selezionare **Avanti**.
8. Attendere che i numeri di telefono vengano riservati e quindi visualizzare i numeri ottenuti. Se sembra tutto corretto, selezionare **Esegui l'ordine** e quindi **Fine**.
