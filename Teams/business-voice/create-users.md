---
title: Creare Microsoft 365 utenti, aggiungere Teams Telefono con le licenze del pacchetto Piano per chiamate e assegnare numeri di telefono
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
ms.localizationpriority: medium
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
description: Informazioni su come creare e assegnare licenze Teams Sistema telefonico utenti del pacchetto Piano per chiamate e assegnare loro numeri di telefono.
appliesto:
- Microsoft Teams
ms.openlocfilehash: eb60d60a12949cbb2a0b9ac60e727cfab393de12
ms.sourcegitcommit: e86e3824c300c24e022d5cb1848338278a5a96a8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/03/2022
ms.locfileid: "63053275"
---
# <a name="create-and-license-teams-phone-system-with-calling-plan-bundle-users-and-assign-them-phone-numbers"></a>Creare e assegnare licenze Teams Sistema telefonico utenti del pacchetto Piano per chiamate e assegnare loro i numeri di telefono

Per usare il pacchetto Teams Sistema telefonico piano per chiamate, è necessario un account Microsoft 365 con Teams Telefono con licenze del pacchetto Piano per chiamate. Se si ha un account e le licenze, è possibile iniziare ad assegnare numeri di telefono.

## <a name="create-and-license-users"></a>Creare utenti e assegnare licenze

Seguire i passaggi in [Aggiungere utenti singolarmente o in blocco ](/microsoft-365/admin/add-users/add-users) e [Assegnare licenze agli utenti](/microsoft-365/admin/manage/assign-licenses-to-users).

> [!NOTE]
> Nel riquadro **Assegna licenze di** prodotto selezionare Teams Telefono **piano per chiamate**.

## <a name="assign-phone-numbers-to-users"></a>Assegnare numeri di telefono agli utenti

Dopo aver creato gli utenti e averle Teams Telefono con la licenza del bundle Piano per chiamate, è possibile assegnare loro i numeri di telefono. È necessario un numero di telefono non assegnato per ogni utente che deve effettuare o ricevere chiamate da numeri di telefono esterni. Se non si hanno numeri di telefono non assegnati sufficienti, vedere [Ottenere altri numeri di telefono](#get-more-phone-numbers) più avanti in questo articolo.

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
