---
title: Report utenti bloccati PSTN di Microsoft Teams
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
description: Usare il report utenti bloccati PSTN nell'interfaccia di amministrazione di Microsoft teams per ottenere una panoramica degli utenti del team dell'organizzazione bloccati dall'esecuzione di chiamate PSTN.
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
# <a name="microsoft-teams-pstn-blocked-users-report"></a><span data-ttu-id="1977d-103">Report utenti bloccati PSTN di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1977d-103">Microsoft Teams PSTN blocked users report</span></span>

<span data-ttu-id="1977d-104">Il report utenti bloccati PSTN nell'interfaccia di amministrazione di Microsoft teams Mostra gli utenti dell'organizzazione bloccati dall'esecuzione di chiamate PSTN in teams.</span><span class="sxs-lookup"><span data-stu-id="1977d-104">The PSTN blocked users report in the Microsoft Teams admin center shows you the users in your organization who are blocked from making PSTN calls in Teams.</span></span> <span data-ttu-id="1977d-105">È possibile visualizzare altre informazioni su ogni utente bloccato, incluso il numero di telefono assegnato e il motivo per cui sono stati bloccati dall'esecuzione delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="1977d-105">You can view more information about each blocked user, including their assigned phone number and the reason they were blocked from making calls.</span></span>

## <a name="view-the-pstn-blocked-users-report"></a><span data-ttu-id="1977d-106">Visualizzare il report utenti bloccati PSTN</span><span class="sxs-lookup"><span data-stu-id="1977d-106">View the PSTN blocked users report</span></span>

<span data-ttu-id="1977d-107">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams fare clic su **analisi &** report  >  **sull'utilizzo** dei rapporti.</span><span class="sxs-lookup"><span data-stu-id="1977d-107">In the left navigation of the Microsoft Teams admin center, click **Analytics & reports** > **Usage reports**.</span></span> <span data-ttu-id="1977d-108">Nella scheda **Visualizza report** , in **report**, selezionare **utenti bloccati PSTN** e quindi fare clic su **Esegui report**.</span><span class="sxs-lookup"><span data-stu-id="1977d-108">On the **View reports** tab, under **Report**, select **PSTN blocked users**, and then click **Run report**.</span></span>

<span data-ttu-id="1977d-109">![Screenshot del report degli utenti bloccati PSTN nell'interfaccia di amministrazione](../media/teams-reports-pstn-blocked-users-with-callouts.png "Screenshot del report utenti bloccati PSTN nell'interfaccia di amministrazione di Microsoft teams con callout numerati")</span><span class="sxs-lookup"><span data-stu-id="1977d-109">![Screenshot of the PSTN blocked users report report in the admin center](../media/teams-reports-pstn-blocked-users-with-callouts.png "Screenshot of the PSTN blocked users report in the Microsoft Teams admin center with numbered callouts")</span></span>

## <a name="interpret-the-report"></a><span data-ttu-id="1977d-110">Interpretare il report</span><span class="sxs-lookup"><span data-stu-id="1977d-110">Interpret the report</span></span>

|<span data-ttu-id="1977d-111">Callout</span><span class="sxs-lookup"><span data-stu-id="1977d-111">Callout</span></span> |<span data-ttu-id="1977d-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1977d-112">Description</span></span>  |
|--------|-------------|
|<span data-ttu-id="1977d-113">**1**</span><span class="sxs-lookup"><span data-stu-id="1977d-113">**1**</span></span>   |<span data-ttu-id="1977d-114">Ogni report ha una data per quando è stata generata.</span><span class="sxs-lookup"><span data-stu-id="1977d-114">Each report has a date for when it was generated.</span></span> <span data-ttu-id="1977d-115">In genere, i report presentano una latenza di 24-48 ore dal momento dell'attività.</span><span class="sxs-lookup"><span data-stu-id="1977d-115">The reports usually reflect a 24 to 48 hour latency from time of activity.</span></span> |
|<span data-ttu-id="1977d-116">**2**</span><span class="sxs-lookup"><span data-stu-id="1977d-116">**2**</span></span>   |<span data-ttu-id="1977d-117">L'asse X è la data.</span><span class="sxs-lookup"><span data-stu-id="1977d-117">The X axis is the date.</span></span> <span data-ttu-id="1977d-118">L'asse Y è il numero di utenti.</span><span class="sxs-lookup"><span data-stu-id="1977d-118">The Y axis is the number of users.</span></span> <br><span data-ttu-id="1977d-119">Posizionare il puntatore del mouse sul punto in una data specificata per visualizzare il numero di utenti bloccati in tale data.</span><span class="sxs-lookup"><span data-stu-id="1977d-119">Hover over the dot on a given date to see the number of users blocked on that date.</span></span> |
|<span data-ttu-id="1977d-120">**3**</span><span class="sxs-lookup"><span data-stu-id="1977d-120">**3**</span></span>   |<span data-ttu-id="1977d-121">La tabella fornisce una ripartizione di tutti gli utenti bloccati dall'esecuzione di chiamate PSTN.</span><span class="sxs-lookup"><span data-stu-id="1977d-121">The table gives a breakdown of all users who are blocked from making PSTN calls.</span></span>  <span data-ttu-id="1977d-122">Mostra tutti gli utenti con sistema telefonico o servizi di audioconferenza assegnati e fornisce altre informazioni su ogni utente.</span><span class="sxs-lookup"><span data-stu-id="1977d-122">It shows all users who have Phone System or Audio Conferencing assigned and gives you more information about each user.</span></span> <ul><li><span data-ttu-id="1977d-123">**Nome visualizzato** è il nome visualizzato dell'utente.</span><span class="sxs-lookup"><span data-stu-id="1977d-123">**Display name** is the display name of the user.</span></span> <span data-ttu-id="1977d-124">È possibile fare clic sul nome visualizzato per accedere alla pagina di impostazione dell'utente nell'interfaccia di amministrazione di Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="1977d-124">You can click the display name to go to the user's setting page in the Microsoft Teams admin center.</span></span> </li> <li><span data-ttu-id="1977d-125">**Telefono** è il numero assegnato all'utente.</span><span class="sxs-lookup"><span data-stu-id="1977d-125">**Phone** is the number that's assigned to the user.</span></span></li> <li><span data-ttu-id="1977d-126">Il **motivo bloccato** è il motivo per cui l'utente è bloccato dall'esecuzione delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="1977d-126">**Blocked reason** is the reason the user is blocked from making calls.</span></span></li><li><span data-ttu-id="1977d-127">L' **azione bloccata** indica se l'utente è bloccato o sbloccato dall'esecuzione di chiamate PSTN in teams.</span><span class="sxs-lookup"><span data-stu-id="1977d-127">**Blocked action**  tells you whether the user is blocked or unblocked from making PSTN calls in Teams.</span></span></li> <li><span data-ttu-id="1977d-128">**Ora bloccata** è la data e l'ora (UTC) in cui l'utente è stato bloccato per effettuare chiamate.</span><span class="sxs-lookup"><span data-stu-id="1977d-128">**Blocked time** is the date and time (UTC) that the user was blocked from making calls.</span></span></li></li> </ul><span data-ttu-id="1977d-129">Per visualizzare le informazioni desiderate nella tabella, assicurarsi di aggiungere le colonne alla tabella.</span><span class="sxs-lookup"><span data-stu-id="1977d-129">To see the information that you want in the table, make sure to add the columns to the table.</span></span> |
|<span data-ttu-id="1977d-130">**4**</span><span class="sxs-lookup"><span data-stu-id="1977d-130">**4**</span></span>   |<span data-ttu-id="1977d-131">Selezionare **modifica colonne** per aggiungere o rimuovere colonne nella tabella.</span><span class="sxs-lookup"><span data-stu-id="1977d-131">Select **Edit columns** to add or remove columns in the table.</span></span>|
|<span data-ttu-id="1977d-132">**5**</span><span class="sxs-lookup"><span data-stu-id="1977d-132">**5**</span></span>   |<span data-ttu-id="1977d-133">Selezionare **schermo intero** per visualizzare il report in modalità schermo intero.</span><span class="sxs-lookup"><span data-stu-id="1977d-133">Select **Full screen** to view the report in full screen mode.</span></span>|

## <a name="related-topics"></a><span data-ttu-id="1977d-134">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="1977d-134">Related topics</span></span>

- [<span data-ttu-id="1977d-135">Analisi e creazione di report in teams</span><span class="sxs-lookup"><span data-stu-id="1977d-135">Teams analytics and reporting</span></span>](teams-reporting-reference.md)