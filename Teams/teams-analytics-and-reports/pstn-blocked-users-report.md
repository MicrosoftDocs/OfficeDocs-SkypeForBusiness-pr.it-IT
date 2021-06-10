---
title: Microsoft Teams Report utenti bloccati PSTN
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: v-rifer
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
MS.collection:
- M365-voice
description: Usare il report Utenti bloccati PSTN nell'interfaccia di amministrazione di Microsoft Teams per ottenere una panoramica degli utenti Teams dell'organizzazione a cui è impedito di effettuare chiamate PSTN.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ed775c3796e40a775b3be2b78f22e162a047bf78
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809336"
---
# <a name="microsoft-teams-pstn-blocked-users-report"></a><span data-ttu-id="18f82-103">Microsoft Teams Report utenti bloccati PSTN</span><span class="sxs-lookup"><span data-stu-id="18f82-103">Microsoft Teams PSTN blocked users report</span></span>

<span data-ttu-id="18f82-104">Il report Utenti bloccati PSTN nell'interfaccia di amministrazione di Microsoft Teams mostra gli utenti dell'organizzazione a cui è impedito di effettuare chiamate PSTN in Teams.</span><span class="sxs-lookup"><span data-stu-id="18f82-104">The PSTN blocked users report in the Microsoft Teams admin center shows you the users in your organization who are blocked from making PSTN calls in Teams.</span></span> <span data-ttu-id="18f82-105">È possibile visualizzare altre informazioni su ogni utente bloccato, incluso il numero di telefono assegnato e il motivo per cui è stato impedito di effettuare chiamate.</span><span class="sxs-lookup"><span data-stu-id="18f82-105">You can view more information about each blocked user, including their assigned phone number and the reason they were blocked from making calls.</span></span>

## <a name="view-the-pstn-blocked-users-report"></a><span data-ttu-id="18f82-106">Visualizzare il report degli utenti bloccati PSTN</span><span class="sxs-lookup"><span data-stu-id="18f82-106">View the PSTN blocked users report</span></span>

<span data-ttu-id="18f82-107">Nel riquadro di spostamento sinistro dell'interfaccia Microsoft Teams di amministrazione fare clic su Analisi & **report**  >  **utilizzo**.</span><span class="sxs-lookup"><span data-stu-id="18f82-107">In the left navigation of the Microsoft Teams admin center, click **Analytics & reports** > **Usage reports**.</span></span> <span data-ttu-id="18f82-108">Nella scheda **Visualizza report,** in **Report,** selezionare **Utenti bloccati PSTN** e quindi fare clic su **Esegui report.**</span><span class="sxs-lookup"><span data-stu-id="18f82-108">On the **View reports** tab, under **Report**, select **PSTN blocked users**, and then click **Run report**.</span></span>

<span data-ttu-id="18f82-109">![Screenshot del report degli utenti bloccati PSTN nell'interfaccia di amministrazione](../media/teams-reports-pstn-blocked-users-with-callouts.png "Screenshot del report Degli utenti bloccati PSTN nell'interfaccia di amministrazione Microsoft Teams con callout numerati")</span><span class="sxs-lookup"><span data-stu-id="18f82-109">![Screenshot of the PSTN blocked users report report in the admin center](../media/teams-reports-pstn-blocked-users-with-callouts.png "Screenshot of the PSTN blocked users report in the Microsoft Teams admin center with numbered callouts")</span></span>

## <a name="interpret-the-report"></a><span data-ttu-id="18f82-110">Interpretare il report</span><span class="sxs-lookup"><span data-stu-id="18f82-110">Interpret the report</span></span>

|<span data-ttu-id="18f82-111">Callout</span><span class="sxs-lookup"><span data-stu-id="18f82-111">Callout</span></span> |<span data-ttu-id="18f82-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="18f82-112">Description</span></span>  |
|--------|-------------|
|<span data-ttu-id="18f82-113">**1**</span><span class="sxs-lookup"><span data-stu-id="18f82-113">**1**</span></span>   |<span data-ttu-id="18f82-114">Ogni report ha una data in cui è stato generato.</span><span class="sxs-lookup"><span data-stu-id="18f82-114">Each report has a date for when it was generated.</span></span> <span data-ttu-id="18f82-115">In genere, i report presentano una latenza di 24-48 ore dal momento dell'attività.</span><span class="sxs-lookup"><span data-stu-id="18f82-115">The reports usually reflect a 24 to 48 hour latency from time of activity.</span></span> |
|<span data-ttu-id="18f82-116">**2**</span><span class="sxs-lookup"><span data-stu-id="18f82-116">**2**</span></span>   |<span data-ttu-id="18f82-117">L'asse X è la data.</span><span class="sxs-lookup"><span data-stu-id="18f82-117">The X axis is the date.</span></span> <span data-ttu-id="18f82-118">L'asse Y è il numero di utenti.</span><span class="sxs-lookup"><span data-stu-id="18f82-118">The Y axis is the number of users.</span></span> <br><span data-ttu-id="18f82-119">Posizionare il puntatore del mouse sul punto in una data specifica per visualizzare il numero di utenti bloccati in tale data.</span><span class="sxs-lookup"><span data-stu-id="18f82-119">Hover over the dot on a given date to see the number of users blocked on that date.</span></span> |
|<span data-ttu-id="18f82-120">**3**</span><span class="sxs-lookup"><span data-stu-id="18f82-120">**3**</span></span>   |<span data-ttu-id="18f82-121">La tabella fornisce una suddivisione di tutti gli utenti a cui è impedito di effettuare chiamate PSTN.</span><span class="sxs-lookup"><span data-stu-id="18f82-121">The table gives a breakdown of all users who are blocked from making PSTN calls.</span></span>  <span data-ttu-id="18f82-122">Mostra tutti gli utenti a cui sono Sistema telefonico o audioconferenze e fornisce altre informazioni su ogni utente.</span><span class="sxs-lookup"><span data-stu-id="18f82-122">It shows all users who have Phone System or Audio Conferencing assigned and gives you more information about each user.</span></span> <ul><li><span data-ttu-id="18f82-123">**Nome visualizzato** è il nome visualizzato dell'utente.</span><span class="sxs-lookup"><span data-stu-id="18f82-123">**Display name** is the display name of the user.</span></span> <span data-ttu-id="18f82-124">È possibile fare clic sul nome visualizzato per passare alla pagina delle impostazioni dell'utente nell'Microsoft Teams di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="18f82-124">You can click the display name to go to the user's setting page in the Microsoft Teams admin center.</span></span> </li> <li><span data-ttu-id="18f82-125">**Telefono** è il numero assegnato all'utente.</span><span class="sxs-lookup"><span data-stu-id="18f82-125">**Phone** is the number that's assigned to the user.</span></span></li> <li><span data-ttu-id="18f82-126">**Il motivo è** il motivo per cui all'utente viene impedito di effettuare chiamate.</span><span class="sxs-lookup"><span data-stu-id="18f82-126">**Blocked reason** is the reason the user is blocked from making calls.</span></span></li><li><span data-ttu-id="18f82-127">**Azione bloccata** indica se l'utente è bloccato o sbloccato dall'esecuzione di chiamate PSTN in Teams.</span><span class="sxs-lookup"><span data-stu-id="18f82-127">**Blocked action**  tells you whether the user is blocked or unblocked from making PSTN calls in Teams.</span></span></li> <li><span data-ttu-id="18f82-128">**L'ora** bloccata è la data e l'ora (UTC) in cui all'utente è stato impedito di effettuare chiamate.</span><span class="sxs-lookup"><span data-stu-id="18f82-128">**Blocked time** is the date and time (UTC) that the user was blocked from making calls.</span></span></li></li> </ul><span data-ttu-id="18f82-129">Per visualizzare le informazioni desiderate nella tabella, assicurarsi di aggiungere le colonne alla tabella.</span><span class="sxs-lookup"><span data-stu-id="18f82-129">To see the information that you want in the table, make sure to add the columns to the table.</span></span> |
|<span data-ttu-id="18f82-130">**4**</span><span class="sxs-lookup"><span data-stu-id="18f82-130">**4**</span></span>   |<span data-ttu-id="18f82-131">Selezionare **Modifica colonne** per aggiungere o rimuovere colonne nella tabella.</span><span class="sxs-lookup"><span data-stu-id="18f82-131">Select **Edit columns** to add or remove columns in the table.</span></span>|
|<span data-ttu-id="18f82-132">**5**</span><span class="sxs-lookup"><span data-stu-id="18f82-132">**5**</span></span>   |<span data-ttu-id="18f82-133">Selezionare **Schermo intero** per visualizzare il report in modalità a schermo intero.</span><span class="sxs-lookup"><span data-stu-id="18f82-133">Select **Full screen** to view the report in full screen mode.</span></span>|

## <a name="related-topics"></a><span data-ttu-id="18f82-134">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="18f82-134">Related topics</span></span>

- <span data-ttu-id="18f82-135">[Analisi e creazione dei report di Teams](teams-reporting-reference.md).</span><span class="sxs-lookup"><span data-stu-id="18f82-135">[Teams analytics and reporting](teams-reporting-reference.md)</span></span>