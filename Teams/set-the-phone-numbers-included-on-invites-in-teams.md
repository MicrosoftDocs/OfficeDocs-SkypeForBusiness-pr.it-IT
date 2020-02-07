---
title: Impostare i numeri di telefono inclusi negli inviti in Microsoft Teams
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
description: 'Eseguire la procedura per creare un numero di telefono predefinito per i chiamanti per partecipare a una riunione di Microsoft teams. '
ms.openlocfilehash: b5a43b0987160b87ac4a6e25b10ae6d850612ac1
ms.sourcegitcommit: 8e2fa7b744d0a174b699ae7298d4688b971eeff3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/07/2020
ms.locfileid: "41845237"
---
# <a name="set-the-phone-numbers-included-on-invites-in-microsoft-teams"></a><span data-ttu-id="f52cb-103">Impostare i numeri di telefono inclusi negli inviti in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f52cb-103">Set the phone numbers included on invites in Microsoft Teams</span></span>

<span data-ttu-id="f52cb-104">I servizi di audioconferenza in Office 365 consentono agli utenti dell'organizzazione di creare riunioni di Microsoft teams e quindi consentire agli utenti di accedere a tali riunioni con un telefono.</span><span class="sxs-lookup"><span data-stu-id="f52cb-104">Audio Conferencing in Office 365 enables users in your organization to create Microsoft Teams meetings, and then allow users to dial in to those meetings using a phone.</span></span>
  
<span data-ttu-id="f52cb-105">Un ponte per conferenze offre un insieme di numeri di telefono di accesso esterno per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f52cb-105">A conferencing bridge gives you a set of dial-in phone numbers for your organization.</span></span> <span data-ttu-id="f52cb-106">Tutti questi numeri possono essere utilizzati per accedere alle riunioni create dall'organizzatore, ma è possibile selezionare quelli che verranno inclusi negli inviti alle riunioni.</span><span class="sxs-lookup"><span data-stu-id="f52cb-106">All of them can be used to join the meetings that a meeting organizer has created, but you can select which ones will be included on their meeting invites.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f52cb-107">Vi è un massimo per organizzatore di un numero a pagamento e un numero verde nell'invito alla riunione, ma è disponibile anche un collegamento nella parte inferiore di ogni invito che consente di aprire l'elenco completo di tutti i numeri di telefono di accesso esterno che possono essere utilizzati per accedere ad una riunione.</span><span class="sxs-lookup"><span data-stu-id="f52cb-107">There can be a maximum of one toll and one toll-free phone number on the meeting invite for a meeting organizer, but there is also a link located at the bottom of each meeting invite that opens the full list of all dial-in phone numbers that can be used to join a meeting.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="initial-assignment-of-phone-numbers-that-are-included-in-the-meeting-invites-for-new-users"></a><span data-ttu-id="f52cb-108">Assegnazione iniziale dei numeri di telefono inclusi negli inviti alla riunione per i nuovi utenti</span><span class="sxs-lookup"><span data-stu-id="f52cb-108">Initial assignment of phone numbers that are included in the meeting invites for new users</span></span>

<span data-ttu-id="f52cb-109">I numeri di telefono inclusi negli inviti alle riunioni degli utenti abilitati per i servizi di audioconferenza sono definiti dal numero di telefono predefinito per i servizi di conferenza e dalle impostazioni predefinite dell'utente del numero di telefono gratuito per i servizi di conferenza.</span><span class="sxs-lookup"><span data-stu-id="f52cb-109">The phone numbers that get included in the meeting invites of users enabled for Audio Conferencing are defined by the default conferencing toll phone number and the default conferencing toll-free phone number user's settings.</span></span> <span data-ttu-id="f52cb-110">Ogni impostazione specifica il numero verde e il pedaggio che verrà incluso nell'invito alla riunione di un utente specifico.</span><span class="sxs-lookup"><span data-stu-id="f52cb-110">Each setting specifies which toll and toll-free number will be included in the meeting invite of a given user.</span></span> <span data-ttu-id="f52cb-111">Come indicato sopra, ogni invito alla riunione contiene un numero a pagamento, un numero verde facoltativo e un collegamento che apre l'elenco completo di tutti i numeri di telefono di accesso esterno che possono essere usati per partecipare a una determinata riunione.</span><span class="sxs-lookup"><span data-stu-id="f52cb-111">As noted above, each meeting invite contains one toll number, one optional toll-free number and a link that opens the full list of all dial-in phone numbers that can be used to join a given meeting.</span></span>

<span data-ttu-id="f52cb-112">Per un nuovo utente, i numeri a pagamento predefiniti per i servizi di conferenza vengono assegnati in base al paese impostato nel profilo di Office 365 dell'utente quando l'utente è abilitato per il servizio di audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="f52cb-112">For a new user, the default conferencing toll numbers is assigned based on the country that is set in the Office 365 profile of the user when the user is enabled for the Audio Conferencing service.</span></span> <span data-ttu-id="f52cb-113">Se nel Bridge di conferenza è presente un numero a pagamento che corrisponde al paese dell'utente, tale numero verrà assegnato automaticamente come numero di pedaggio predefinito per l'utente.</span><span class="sxs-lookup"><span data-stu-id="f52cb-113">If there is a toll number in the conference bridge that matches the country of the user, that number will be automatically assigned as the default toll number of the user.</span></span> <span data-ttu-id="f52cb-114">Se non è presente, il numero definito come numero di pedaggio predefinito del Bridge di conferenza verrà assegnato come numero di pedaggio predefinito per l'utente.</span><span class="sxs-lookup"><span data-stu-id="f52cb-114">If there isn't one, the number that is defined as the default toll number of the conference bridge will be assigned as the default toll number of the user.</span></span>  

<span data-ttu-id="f52cb-115">Quando l'utente è abilitato per il servizio di audioconferenza, il numero di telefono predefinito e il numero verde dell'utente possono essere modificati dall'amministratore del tenant dai valori iniziali in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="f52cb-115">Once the user is enabled for the Audio Conferencing service, the default toll and toll-free phone numbers of the user can be changed by the tenant administrator from their initial values at any moment.</span></span>

## <a name="set-or-change-the-default-audio-conferencing-phone-number-for-a-meeting-organizer-or-user"></a><span data-ttu-id="f52cb-116">Impostare o modificare il numero di telefono predefinito per l'audioconferenza per un organizzatore o un utente di una riunione</span><span class="sxs-lookup"><span data-stu-id="f52cb-116">Set or change the default audio conferencing phone number for a meeting organizer or user</span></span>

<span data-ttu-id="f52cb-117">![Icona che mostra il logo](media/teams-logo-30x30.png) di Microsoft teams **con l'interfaccia di amministrazione di Microsoft teams**</span><span class="sxs-lookup"><span data-stu-id="f52cb-117">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="f52cb-118">Nella barra di spostamento sinistra fare clic su **utenti**.</span><span class="sxs-lookup"><span data-stu-id="f52cb-118">In the left navigation, click **Users**.</span></span>

    ![Mostra la selezione degli utenti nell'interfaccia di amministrazione di Microsoft Teams](media/teams-set-phone-numbers-on-invites-image1.png)

2. <span data-ttu-id="f52cb-120">Fare clic sul nome utente nell'elenco degli utenti disponibili.</span><span class="sxs-lookup"><span data-stu-id="f52cb-120">Click the user name from the list of available users.</span></span>

3. <span data-ttu-id="f52cb-121">Accanto a servizi di **audioconferenza**fare clic su **modifica**.</span><span class="sxs-lookup"><span data-stu-id="f52cb-121">Next to **Audio Conferencing**, click **Edit**.</span></span> 
    
    ![Fare clic su Modifica accanto a audioconferenza](media/teams-set-phone-numbers-on-invites-image3.png)

4. <span data-ttu-id="f52cb-123">Usare il **numero a pagamento** o i campi **numero verde** per immettere i numeri per l'utente.</span><span class="sxs-lookup"><span data-stu-id="f52cb-123">Use the **Toll number** or **Toll-free number** fields to enter the numbers for the user.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="f52cb-124">Quando si modificano le impostazioni di conferenza audio di un utente, le riunioni di Microsoft teams e future devono essere aggiornate e inviate ai partecipanti.</span><span class="sxs-lookup"><span data-stu-id="f52cb-124">When you change a user's audio conferencing settings, recurring and future Microsoft Teams meetings must be updated and sent to attendees.</span></span> 

## <a name="want-to-use-windows-powershell"></a><span data-ttu-id="f52cb-125">Desideri utilizzare Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="f52cb-125">Want to use Windows PowerShell?</span></span>

<span data-ttu-id="f52cb-p104">Windows PowerShell riguarda la gestione degli utenti e le azioni che sono autorizzati o meno a eseguire. Con Windows PowerShell puoi gestire Office 365 tramite un unico punto di amministrazione, che ti agevola il lavoro quotidiano quando hai molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedi i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="f52cb-p104">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="f52cb-129">Sei motivi per utilizzare Windows PowerShell per gestire Office 365</span><span class="sxs-lookup"><span data-stu-id="f52cb-129">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="f52cb-130">Modi migliori per gestire Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f52cb-130">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="f52cb-131">Per altre informazioni su Windows PowerShell, vedere la pagina di [riferimento di PowerShell per Microsoft teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="f52cb-131">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span> 
  
    
## <a name="related-topics"></a><span data-ttu-id="f52cb-132">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="f52cb-132">Related topics</span></span>

[<span data-ttu-id="f52cb-133">Provare o acquistare le audioconferenze in Office 365</span><span class="sxs-lookup"><span data-stu-id="f52cb-133">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)

[<span data-ttu-id="f52cb-134">Cambiare i numeri di telefono del bridge per i servizi di audioconferenza</span><span class="sxs-lookup"><span data-stu-id="f52cb-134">Change the phone numbers on your Audio Conferencing bridge</span></span>](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)
