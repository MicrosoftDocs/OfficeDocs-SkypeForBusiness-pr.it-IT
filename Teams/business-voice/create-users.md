---
title: Creare utenti di Microsoft 365, aggiungere licenze di Business Voice e assegnare numeri di telefono
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
localization_priority: Priority
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: ''
appliesto:
- Microsoft Teams
ms.openlocfilehash: cb8277c11cbcc459da9da8fd8d4f5b9c329470f3
ms.sourcegitcommit: 9bead87a7f4c4e71f19f8980e9dce2b979735055
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2020
ms.locfileid: "41269282"
---
# <a name="create-and-license-business-voice-users-and-assign-them-phone-numbers"></a>Creare utenti e assegnare loro licenze di Business Voice e numeri di telefono

Per usare :::no-loc text="Microsoft 365 Business Voice":::, è necessario un account :::no-loc text="Microsoft 365"::: che abbia una licenza di :::no-loc text="Microsoft 365 Business Voice with SMS":::. Quando si ha un account e una licenza, è possibile assegnarvi un numero di telefono.

## <a name="create-and-license-users"></a>Creare utenti e assegnare licenze

Seguire i passaggi descritti in [Aggiungere utenti singolarmente o in blocco a :::no-loc text="Office 365":::](https://docs.microsoft.com/office365/admin/add-users/add-users).

> [!NOTE]
> Nel riquadro **Assegna le licenze dei prodotti** selezionare **:::no-loc text="Microsoft 365 Business Voice with SMS":::**.

## <a name="assign-phone-numbers-to-users"></a>Assegnare numeri di telefono agli utenti

Dopo aver creato gli utenti e aver assegnato loro una licenza di :::no-loc text="Microsoft 365 Business Voice with SMS":::, è possibile assegnare loro un numero di telefono. È necessario un numero di telefono non assegnato per ogni utente che deve effettuare o ricevere chiamate da numeri di telefono esterni. Se non si hanno numeri di telefono non assegnati sufficienti, vedere [Ottenere altri numeri di telefono](#get-more-phone-numbers) più avanti in questo articolo.

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
