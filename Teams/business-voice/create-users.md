---
title: Creare utenti di Microsoft 365, aggiungere licenze di Business Voice e assegnare numeri di telefono
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
localization_priority: Priority
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: ''
appliesto:
- Microsoft Teams
ms.openlocfilehash: 16827d1b90ea07fcd84be286e03f3d3b22a55bd1
ms.sourcegitcommit: 6a4bd155e73ab21944dd5f4f0c776e4cd0508147
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/24/2020
ms.locfileid: "44868633"
---
# <a name="create-and-license-business-voice-users-and-assign-them-phone-numbers"></a>Creare utenti e assegnare loro licenze di Business Voice e numeri di telefono

Per usare :::no-loc text="Microsoft 365 Business Voice":::, è necessario un account :::no-loc text="Microsoft 365"::: che abbia una licenza di :::no-loc text="Microsoft 365 Business Voice":::. Quando si ha un account e una licenza, è possibile assegnarvi un numero di telefono.

## <a name="create-and-license-users"></a>Creare utenti e assegnare licenze

Seguire i passaggi in [Aggiungere utenti singolarmente o in blocco ](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) e [Assegnare licenze agli utenti](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).

> [!NOTE]
> Nel riquadro **Assegna le licenze dei prodotti** selezionare **:::no-loc text="Microsoft 365 Business Voice":::**.

## <a name="assign-phone-numbers-to-users"></a>Assegnare numeri di telefono agli utenti

Dopo aver creato gli utenti e aver assegnato loro una licenza di :::no-loc text="Microsoft 365 Business Voice":::, è possibile assegnare loro un numero di telefono. È necessario un numero di telefono non assegnato per ogni utente che deve effettuare o ricevere chiamate da numeri di telefono esterni. Se non si hanno numeri di telefono non assegnati sufficienti, vedere [Ottenere altri numeri di telefono](#get-more-phone-numbers) più avanti in questo articolo.

1. Passare a https://admin.teams.microsoft.com.
2. Immettere un nome e una descrizione per la richiesta di un numero di telefono.
3. Selezionare **Vocale** > **Numeri telefonici**.
4. Selezionare un numero di telefono che si vuole assegnare a un utente e quindi **Modifica**.
5. Nel riquadro **Modifica** immettere il nome dell'utente a cui si vuole assegnare il numero in **Assegnato a**. Selezionare quindi **Assegna**.
6. In **Posizione di emergenza** immettere il luogo in cui si trova l'utente e quindi selezionare **Applica**

## <a name="get-more-phone-numbers"></a>Ottenere altri numeri di telefono

Se non si hanno abbastanza numeri di telefono da assegnare ai nuovi utenti, è possibile ottenerne altri. Potrebbe essere necessario attendere fino a 24 ore prima che i numeri siano resi disponibili.

1. Passare a https://admin.teams.microsoft.com.
2. Immettere un nome e una descrizione per la richiesta di un numero di telefono.
3. Selezionare **Vocale** > **Numeri di telefono** > **Aggiungi**.
4. Selezionare il Paese o l'area geografica per il numero di telefono.
5. In **Tipo di numero** selezionare **Utente (abbonato)**.
6. In **Posizione** cercare la posizione dell'utente e selezionarla. È anche possibile scegliere **Aggiungi una posizione**.
7. Scegliere un prefisso, immettere il numero di numeri di telefono necessari e quindi selezionare **Avanti**.
8. Attendere che i numeri di telefono vengano riservati e quindi visualizzare i numeri ottenuti. Se sembra tutto corretto, selezionare **Esegui l'ordine** e quindi **Fine**.
