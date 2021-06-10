---
title: Impostare i numeri di telefono inclusi negli inviti
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 32954439-d365-4125-872f-b37466ecb035
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Seguire questa procedura per creare un numero di telefono predefinito per consentire ai chiamanti di partecipare a una Microsoft Teams riunione.
ms.openlocfilehash: 476075ccf5e261695564b78ec084605af9e6898c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117174"
---
# <a name="set-the-phone-numbers-included-on-invites-in-microsoft-teams"></a><span data-ttu-id="888e4-103">Impostare i numeri di telefono inclusi negli inviti in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="888e4-103">Set the phone numbers included on invites in Microsoft Teams</span></span>

<span data-ttu-id="888e4-104">L'audioconferenza in Microsoft 365 e Office 365 consente agli utenti dell'organizzazione di creare riunioni Microsoft Teams e quindi consentire agli utenti di accedere a tali riunioni usando un telefono.</span><span class="sxs-lookup"><span data-stu-id="888e4-104">Audio Conferencing in Microsoft 365 and Office 365 enables users in your organization to create Microsoft Teams meetings, and then allow users to dial in to those meetings using a phone.</span></span>
  
<span data-ttu-id="888e4-105">Un ponte per conferenze offre un insieme di numeri di telefono di accesso esterno per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="888e4-105">A conferencing bridge gives you a set of dial-in phone numbers for your organization.</span></span> <span data-ttu-id="888e4-106">Tutti questi numeri possono essere utilizzati per accedere alle riunioni create dall'organizzatore, ma è possibile selezionare quelli che verranno inclusi negli inviti alle riunioni.</span><span class="sxs-lookup"><span data-stu-id="888e4-106">All of them can be used to join the meetings that a meeting organizer has created, but you can select which ones will be included on their meeting invites.</span></span>
  
> [!NOTE]
> <span data-ttu-id="888e4-107">Vi è un massimo per organizzatore di un numero a pagamento e un numero verde nell'invito alla riunione, ma è disponibile anche un collegamento nella parte inferiore di ogni invito che consente di aprire l'elenco completo di tutti i numeri di telefono di accesso esterno che possono essere utilizzati per accedere ad una riunione.</span><span class="sxs-lookup"><span data-stu-id="888e4-107">There can be a maximum of one toll and one toll-free phone number on the meeting invite for a meeting organizer, but there is also a link located at the bottom of each meeting invite that opens the full list of all dial-in phone numbers that can be used to join a meeting.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="initial-assignment-of-phone-numbers-that-are-included-in-the-meeting-invites-for-new-users"></a><span data-ttu-id="888e4-108">Assegnazione iniziale dei numeri di telefono inclusi negli inviti alla riunione per i nuovi utenti</span><span class="sxs-lookup"><span data-stu-id="888e4-108">Initial assignment of phone numbers that are included in the meeting invites for new users</span></span>

<span data-ttu-id="888e4-109">I numeri di telefono inclusi negli inviti alle riunioni degli utenti abilitati per le audioconferenze sono definiti dal numero di telefono a numero verde di conferenza predefinito e dalle impostazioni predefinite dell'utente con numero verde per le conferenze.</span><span class="sxs-lookup"><span data-stu-id="888e4-109">The phone numbers that get included in the meeting invites of users enabled for Audio Conferencing are defined by the default conferencing toll phone number and the default conferencing toll-free phone number user's settings.</span></span> <span data-ttu-id="888e4-110">Ogni impostazione specifica quale numero a pedaggio e numero verde verrà incluso nell'invito alla riunione di un determinato utente.</span><span class="sxs-lookup"><span data-stu-id="888e4-110">Each setting specifies which toll and toll-free number will be included in the meeting invite of a given user.</span></span> <span data-ttu-id="888e4-111">Come indicato in precedenza, ogni invito alla riunione contiene un numero a pedaggio, un numero verde facoltativo e un collegamento che apre l'elenco completo di tutti i numeri di telefono di accesso esterno che possono essere usati per partecipare a una determinata riunione.</span><span class="sxs-lookup"><span data-stu-id="888e4-111">As noted above, each meeting invite contains one toll number, one optional toll-free number and a link that opens the full list of all dial-in phone numbers that can be used to join a given meeting.</span></span>

<span data-ttu-id="888e4-112">Per un nuovo utente, i numeri a pedaggio di conferenza predefiniti vengono assegnati in base alla posizione di utilizzo impostata nell'interfaccia di amministrazione di Microsoft 365 dell'utente quando l'utente è abilitato per il servizio di audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="888e4-112">For a new user, the default conferencing toll numbers is assigned based on the Usage Location that is set in the Microsoft 365 administration center of the user when the user is enabled for the Audio Conferencing service.</span></span> <span data-ttu-id="888e4-113">Se nel bridge di conferenza è presente un numero a pedaggio corrispondente al paese dell'utente, tale numero verrà assegnato automaticamente come numero a pedaggio predefinito dell'utente.</span><span class="sxs-lookup"><span data-stu-id="888e4-113">If there is a toll number in the conference bridge that matches the country of the user, that number will be automatically assigned as the default toll number of the user.</span></span> <span data-ttu-id="888e4-114">Se non ce n'è uno, il numero definito come numero a pedaggio predefinito del bridge di conferenza verrà assegnato come numero a pedaggio predefinito dell'utente.</span><span class="sxs-lookup"><span data-stu-id="888e4-114">If there isn't one, the number that is defined as the default toll number of the conference bridge will be assigned as the default toll number of the user.</span></span>  

<span data-ttu-id="888e4-115">Dopo aver abilitato l'utente per il servizio di audioconferenza, i numeri di telefono a numero verde e a pedaggio predefiniti dell'utente possono essere modificati dall'amministratore del tenant dai valori iniziali in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="888e4-115">Once the user is enabled for the Audio Conferencing service, the default toll and toll-free phone numbers of the user can be changed by the tenant administrator from their initial values at any moment.</span></span>

## <a name="set-or-change-the-default-audio-conferencing-phone-number-for-a-meeting-organizer-or-user"></a><span data-ttu-id="888e4-116">Impostare o modificare il numero di telefono di audioconferenza predefinito per un organizzatore o un utente della riunione</span><span class="sxs-lookup"><span data-stu-id="888e4-116">Set or change the default audio conferencing phone number for a meeting organizer or user</span></span>

<span data-ttu-id="888e4-117">![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) **Uso dell'interfaccia di amministrazione di Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="888e4-117">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

<span data-ttu-id="888e4-118">Per apportare queste modifiche, è necessario essere un amministratore del servizio Teams.</span><span class="sxs-lookup"><span data-stu-id="888e4-118">You must be a Teams service admin to make these changes.</span></span> <span data-ttu-id="888e4-119">Vedere [Usare i ruoli di amministratore di Teams per gestire Teams](./using-admin-roles.md) per informazioni su come ottenere ruoli e autorizzazioni di amministratore.</span><span class="sxs-lookup"><span data-stu-id="888e4-119">See [Use Teams administrator roles to manage Teams](./using-admin-roles.md) to read about getting admin roles and permissions.</span></span>

1. <span data-ttu-id="888e4-120">Accedere all'interfaccia Microsoft Teams di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="888e4-120">Log in to the Microsoft Teams admin center.</span></span>

2. <span data-ttu-id="888e4-121">Nel riquadro di spostamento sinistro fare clic su **Utenti.**</span><span class="sxs-lookup"><span data-stu-id="888e4-121">In the left navigation, click **Users**.</span></span>

    ![Mostra la selezione di utenti nell'Microsoft Teams di amministrazione](media/Admin-users.png)

3. <span data-ttu-id="888e4-123">Fare clic sul nome utente nell'elenco degli utenti disponibili.</span><span class="sxs-lookup"><span data-stu-id="888e4-123">Click the user name from the list of available users.</span></span>

4. <span data-ttu-id="888e4-124">Accanto a **Audioconferenza** fare clic su **Modifica.**</span><span class="sxs-lookup"><span data-stu-id="888e4-124">Next to **Audio Conferencing**, click **Edit**.</span></span>

    ![Fare clic su Modifica accanto a Audioconferenza](media/teams-set-phone-numbers-on-invites-image3.png)

5. <span data-ttu-id="888e4-126">Usare i campi  **Numero a pedaggio** o Numero verde per immettere i numeri per l'utente.</span><span class="sxs-lookup"><span data-stu-id="888e4-126">Use the **Toll number** or **Toll-free number** fields to enter the numbers for the user.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="888e4-127">Quando si modificano le impostazioni di audioconferenza di un utente, le riunioni ricorrenti e future Microsoft Teams devono essere aggiornate e inviate ai partecipanti.</span><span class="sxs-lookup"><span data-stu-id="888e4-127">When you change a user's audio conferencing settings, recurring and future Microsoft Teams meetings must be updated and sent to attendees.</span></span>

## <a name="want-to-use-windows-powershell"></a><span data-ttu-id="888e4-128">Si vuole usare Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="888e4-128">Want to use Windows PowerShell</span></span>

<span data-ttu-id="888e4-129">Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire.</span><span class="sxs-lookup"><span data-stu-id="888e4-129">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="888e4-130">Con Windows PowerShell, è possibile gestire Microsoft 365 o Office 365 usando un unico punto di amministrazione che consente di semplificare il lavoro quotidiano quando si hanno più attività da eseguire.</span><span class="sxs-lookup"><span data-stu-id="888e4-130">With Windows PowerShell, you can manage Microsoft 365 or Office 365 by using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="888e4-131">Per iniziare a usare Windows PowerShell, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="888e4-131">To get started with Windows PowerShell, see these topics:</span></span>

- [<span data-ttu-id="888e4-132">Sei motivi per utilizzare Windows PowerShell per gestire Office 365</span><span class="sxs-lookup"><span data-stu-id="888e4-132">Why you need to use Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- <span data-ttu-id="888e4-133">[Gestire Office 365 o Microsoft 365 con Windows PowerShell nel modo migliore](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="888e4-133">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>

<span data-ttu-id="888e4-134">Per altre informazioni su Windows PowerShell, vedere [Riferimenti su PowerShell in Microsoft Teams](/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="888e4-134">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="888e4-135">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="888e4-135">Related topics</span></span>

[<span data-ttu-id="888e4-136">Provare o acquistare audioconferenze in Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="888e4-136">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)

[<span data-ttu-id="888e4-137">Cambiare i numeri di telefono del bridge per i servizi di audioconferenza</span><span class="sxs-lookup"><span data-stu-id="888e4-137">Change the phone numbers on your Audio Conferencing bridge</span></span>](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)