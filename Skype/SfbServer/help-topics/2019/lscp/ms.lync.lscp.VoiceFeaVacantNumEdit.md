---
title: Numero di telefono non assegnato Crea nuovo o Modifica esistente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.VoiceFeaVacantNumEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 58903e40-6b93-40d6-88f8-1201743cd9be
ROBOTS: NOINDEX, NOFOLLOW
description: I numeri non assegnati sono numeri di telefono validi per l'organizzazione ma non assegnati a un utente o un telefono. La tabella dei numeri non assegnati identifica come si desidera gestire le chiamata a numeri non assegnati.
ms.openlocfilehash: 49837269f81eaee09a0c191008234345d1d6d19f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51097052"
---
# <a name="unassigned-phone-number-create-new-or-edit-existing"></a><span data-ttu-id="a3dfd-104">Numero di telefono non assegnato: crearne uno nuovo o modificarne uno esistente</span><span class="sxs-lookup"><span data-stu-id="a3dfd-104">Unassigned Phone Number: Create New or Edit Existing</span></span>

> [!NOTE]
> <span data-ttu-id="a3dfd-105">La messaggistica unificata di Exchange rimane disponibile in Skype for Business Server 2019 quando si integra Skype for Business 2019 con Exchange 2013 o Exchange 2016.</span><span class="sxs-lookup"><span data-stu-id="a3dfd-105">Exchange UM remains available in Skype for Business Server 2019 when you integrate Skype for Business 2019 with Exchange 2013 or Exchange 2016.</span></span> <span data-ttu-id="a3dfd-106">A causa delle modifiche apportate al supporto in Exchange 2019, l'integrazione della messaggistica unificata di Exchange viene de-enfatizzata a favore delle funzionalità Cloud Voicemail e Cloud Operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="a3dfd-106">Due to changes in support in Exchange 2019, Exchange UM integration is being de-emphasized in favor of Cloud Voicemail and Cloud Auto Attendant features.</span></span>

<span data-ttu-id="a3dfd-p103">I numeri non assegnati sono numeri di telefono validi per l'organizzazione ma non assegnati a un utente o un telefono. La tabella dei numeri non assegnati identifica come si desidera gestire le chiamata a numeri non assegnati.</span><span class="sxs-lookup"><span data-stu-id="a3dfd-p103">Unassigned numbers are phone numbers that are valid for your organization but are not assigned to a user or a phone. The unassigned number table identifies how you want calls to unassigned numbers to be treated.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a3dfd-p104">Dopo aver creato un nuovo intervallo di numeri non assegnati o averne modificato uno esistente, fare clic su **OK** per tornare alla pagina **Numero non assegnato**, in cui sono elencati tutti gli intervalli di numeri. Le modifiche eseguite nella pagina **Nuovo intervallo di numeri non assegnati** o **Modifica intervallo di numeri non assegnati** non vengono salvate nel database fino a quando non si fa clic su **Salva tutto** nella pagina **Numero non assegnato**.</span><span class="sxs-lookup"><span data-stu-id="a3dfd-p104">When you are finished creating a new unassigned number range or editing an existing one, click **OK** to return to the **Unassigned Number** page that lists all the number ranges. The changes you made on the **New Unassigned Number Range** page or the **Edit Unassigned Number Rage** page are not committed to the database until you click **Commit all** on the **Unassigned Number** page.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="a3dfd-111">Informazioni sull'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="a3dfd-111">UI Reference</span></span>

<span data-ttu-id="a3dfd-112">L'elenco seguente descrive i campi presenti nella pagina.</span><span class="sxs-lookup"><span data-stu-id="a3dfd-112">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="a3dfd-113">**Nome** Digitare un nome descrittivo che identifichi l'intervallo di numeri non assegnati.</span><span class="sxs-lookup"><span data-stu-id="a3dfd-113">**Name** Type a descriptive name that identifies the unassigned number range.</span></span> <span data-ttu-id="a3dfd-114">Una volta salvato l'intervallo, questo nome non potrà essere modificato.</span><span class="sxs-lookup"><span data-stu-id="a3dfd-114">After you save the range, this name cannot be changed.</span></span>

- <span data-ttu-id="a3dfd-115">**Intervallo di numeri** Nel primo campo digitare il numero iniziale dell'intervallo di numeri non assegnati.</span><span class="sxs-lookup"><span data-stu-id="a3dfd-115">**Number range** In the first field, type the beginning number of the unassigned number range.</span></span> <span data-ttu-id="a3dfd-116">Nel secondo campo digitare il numero finale dell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="a3dfd-116">In the second field, type the ending number of the range.</span></span>

  - <span data-ttu-id="a3dfd-117">Il numero iniziale dell'intervallo deve essere minore o uguale al numero finale dell'intervallo stesso.</span><span class="sxs-lookup"><span data-stu-id="a3dfd-117">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

  - <span data-ttu-id="a3dfd-118">Se il numero iniziale o il numero finale dell'intervallo include un numero di interno, devono includerlo entrambi. Il numero di interno deve essere lo stesso per ambedue.</span><span class="sxs-lookup"><span data-stu-id="a3dfd-118">If the beginning number of the range or the ending number of the range includes an extension number, both the beginning number and the ending number of the range must include an extension, and the extension number must be the same for both the beginning number and the ending number.</span></span>

  - <span data-ttu-id="a3dfd-119">Il numero deve corrispondere all'espressione regolare ( `tel:` )?( \+ )? [1-9]\d {0,17} (;ext=[1-9]\d {0,9} )?.</span><span class="sxs-lookup"><span data-stu-id="a3dfd-119">The number must match the regular expression (`tel:`)?(\+)?[1-9]\d{0,17}(;ext=[1-9]\d{0,9})?.</span></span> <span data-ttu-id="a3dfd-120">Questo significa che il numero può iniziare con la stringa 'tel:'.</span><span class="sxs-lookup"><span data-stu-id="a3dfd-120">This means the number may begin with the string 'tel:'.</span></span> <span data-ttu-id="a3dfd-121">Se non si specifica tale stringa, verrà aggiunta automaticamente, ad esempio un segno più (+) e una cifra da 1 a 9.</span><span class="sxs-lookup"><span data-stu-id="a3dfd-121">If you don't specify that string, it will be automatically added for you, such as a plus sign (+), and a digit 1 through 9.</span></span> <span data-ttu-id="a3dfd-122">Il numero di telefono può contenere fino a 17 cifre e può essere seguito da un interno nel formato ;ext= seguito dal numero dell'interno.</span><span class="sxs-lookup"><span data-stu-id="a3dfd-122">The phone number can be up to 17 digits and may be followed by an extension in the format ;ext= followed by the extension number.</span></span>

- <span data-ttu-id="a3dfd-123">**Servizio annunci** Selezionare **Annuncio** per fare in modo che l'applicazione Annuncio gestirà la chiamata in arrivo o la messaggistica unificata di **Exchange** in modo che un Operatore automatico di messaggistica unificata di Exchange gestirà la chiamata in arrivo.</span><span class="sxs-lookup"><span data-stu-id="a3dfd-123">**Announcement service** Select **Announcement** to have the Announcement application handle the incoming call or **Exchange UM** to have an Exchange UM Auto Attendant handle the incoming call.</span></span>

- <span data-ttu-id="a3dfd-124">Se è stato selezionato **Annuncio** per **Servizio Annuncio**:</span><span class="sxs-lookup"><span data-stu-id="a3dfd-124">If you selected **Announcement** for **Announcement service**:</span></span>

  - <span data-ttu-id="a3dfd-125">**FQDN del server di destinazione** Selezionare l'ID del servizio applicazione che esegue l'applicazione Annuncio che gestirà le chiamate in arrivo a questo intervallo di numeri non assegnati.</span><span class="sxs-lookup"><span data-stu-id="a3dfd-125">**FQDN of destination server** Select the service ID of the Application service that runs the Announcement application that will handle incoming calls to this range of unassigned numbers.</span></span>

  - <span data-ttu-id="a3dfd-126">**Annuncio** Selezionare l'annuncio da riprodurre per questo intervallo di numeri non assegnati.</span><span class="sxs-lookup"><span data-stu-id="a3dfd-126">**Announcement** Select the announcement to be played for this range of unassigned numbers.</span></span>

- <span data-ttu-id="a3dfd-127">Se è stata selezionata **Messaggistica unificata di Exchange** per **Servizio Annuncio**:</span><span class="sxs-lookup"><span data-stu-id="a3dfd-127">If you selected **Exchange UM** for **Announcement service**:</span></span>

  - <span data-ttu-id="a3dfd-128">**Operatore automatico numero di telefono** Selezionare il numero di telefono per il servizio di messaggistica unificata di Exchange Operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="a3dfd-128">**Auto Attendant phone number** Select the phone number for the Exchange UM Auto Attendant.</span></span>

<span data-ttu-id="a3dfd-129">Per informazioni dettagliate sulle funzionalità e sulle funzionalità degli annunci, vedere [Plan for the Announcement application in Skype for Business](../../../plan-your-deployment/enterprise-voice-solution/announcement.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="a3dfd-129">For details about Announcement features and capabilities, see [Plan for the Announcement application in Skype for Business](../../../plan-your-deployment/enterprise-voice-solution/announcement.md) in the Planning documentation.</span></span> <span data-ttu-id="a3dfd-130">Per informazioni dettagliate sull'utilizzo di intervalli di numeri non assegnati, vedere [Configure Routing of Unassigned Phone Numbers](/previous-versions/office/lync-server-2013/lync-server-2013-configure-unassigned-phone-numbers) nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="a3dfd-130">For details about working with unassigned number ranges, see [Configure Routing of Unassigned Phone Numbers](/previous-versions/office/lync-server-2013/lync-server-2013-configure-unassigned-phone-numbers) in the Operations documentation.</span></span>