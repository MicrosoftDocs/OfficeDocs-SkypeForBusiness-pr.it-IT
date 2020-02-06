---
title: Numero di telefono non assegnato Crea nuovo o modifica esistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.VoiceFeaVacantNumEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58903e40-6b93-40d6-88f8-1201743cd9be
description: I numeri non assegnati sono numeri di telefono validi per l'organizzazione ma non assegnati a un utente o un telefono. La tabella dei numeri non assegnati identifica come si desidera gestire le chiamata a numeri non assegnati.
ms.openlocfilehash: 27977490b1cd55af9ae3011cfeb56878a5da6876
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41821908"
---
# <a name="unassigned-phone-number-create-new-or-edit-existing"></a><span data-ttu-id="b69e7-104">Numero di telefono non assegnato: crearne uno nuovo o modificarne uno esistente</span><span class="sxs-lookup"><span data-stu-id="b69e7-104">Unassigned Phone Number: Create New or Edit Existing</span></span>

<span data-ttu-id="b69e7-p102">I numeri non assegnati sono numeri di telefono validi per l'organizzazione ma non assegnati a un utente o un telefono. La tabella dei numeri non assegnati identifica come si desidera gestire le chiamata a numeri non assegnati.</span><span class="sxs-lookup"><span data-stu-id="b69e7-p102">Unassigned numbers are phone numbers that are valid for your organization but are not assigned to a user or a phone. The unassigned number table identifies how you want calls to unassigned numbers to be treated.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b69e7-107">Dopo aver creato un nuovo intervallo di numeri non assegnati o averne modificato uno esistente, fare clic su **OK** per tornare alla pagina **numero non assegnati** che elenca tutti gli intervalli di numeri.</span><span class="sxs-lookup"><span data-stu-id="b69e7-107">When you are finished creating a new unassigned number range or editing an existing one, click **OK** to return to the **Unassigned Number** page that lists all the number ranges.</span></span> <span data-ttu-id="b69e7-108">Le modifiche apportate nella pagina **nuovo intervallo di numeri non assegnati** o nella pagina **modifica numero non assegnato non assegnati** non vengono salvate nel database finché non si fa clic su **commit tutto** nella pagina **numero non assegnati** .</span><span class="sxs-lookup"><span data-stu-id="b69e7-108">The changes you made on the **New Unassigned Number Range** page or the **Edit Unassigned Number Rage** page are not committed to the database until you click **Commit all** on the **Unassigned Number** page.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="b69e7-109">Riferimenti UI</span><span class="sxs-lookup"><span data-stu-id="b69e7-109">UI Reference</span></span>

<span data-ttu-id="b69e7-110">L'elenco seguente descrive i campi presenti nella pagina.</span><span class="sxs-lookup"><span data-stu-id="b69e7-110">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="b69e7-111">**Nome** Digitare un nome descrittivo che identifichi l'intervallo di numeri non assegnati.</span><span class="sxs-lookup"><span data-stu-id="b69e7-111">**Name** Type a descriptive name that identifies the unassigned number range.</span></span> <span data-ttu-id="b69e7-112">Dopo aver salvato l'intervallo, non è possibile modificare questo nome.</span><span class="sxs-lookup"><span data-stu-id="b69e7-112">After you save the range, this name cannot be changed.</span></span>

- <span data-ttu-id="b69e7-113">**Intervallo di numeri** Nel primo campo digitare il numero iniziale dell'intervallo di numeri non assegnati.</span><span class="sxs-lookup"><span data-stu-id="b69e7-113">**Number range** In the first field, type the beginning number of the unassigned number range.</span></span> <span data-ttu-id="b69e7-114">Nel secondo campo digitare il numero finale dell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="b69e7-114">In the second field, type the ending number of the range.</span></span>

  - <span data-ttu-id="b69e7-115">Il numero iniziale dell'intervallo deve essere minore o uguale al numero finale dell'intervallo stesso.</span><span class="sxs-lookup"><span data-stu-id="b69e7-115">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

  - <span data-ttu-id="b69e7-116">Se il numero di inizio dell'intervallo o il numero finale dell'intervallo include un numero di interno, sia il numero iniziale che il numero finale dell'intervallo devono includere un'estensione e il numero di interno deve essere uguale sia per il numero iniziale che per il numero finale.</span><span class="sxs-lookup"><span data-stu-id="b69e7-116">If the beginning number of the range or the ending number of the range includes an extension number, both the beginning number and the ending number of the range must include an extension, and the extension number must be the same for both the beginning number and the ending number.</span></span>

  - <span data-ttu-id="b69e7-117">Il numero deve corrispondere all'espressione regolare (Tel:)? \+)? [1-9] \d{0,17}(; EXT = [1-9] \d{0,9})?.</span><span class="sxs-lookup"><span data-stu-id="b69e7-117">The number must match the regular expression (tel:)?(\+)?[1-9]\d{0,17}(;ext=[1-9]\d{0,9})?.</span></span> <span data-ttu-id="b69e7-118">Questo significa che il numero può iniziare con la stringa tel: (se non specifichi la stringa che verrà aggiunta automaticamente), un segno più (+) e una cifra da 1 a 9.</span><span class="sxs-lookup"><span data-stu-id="b69e7-118">This means the number may begin with the string tel: (if you don't specify that string it will be automatically added for you), a plus sign (+), and a digit 1 through 9.</span></span> <span data-ttu-id="b69e7-119">Il numero di telefono può contenere fino a 17 cifre e può essere seguito da un interno nel formato ;ext= seguito dal numero dell'interno.</span><span class="sxs-lookup"><span data-stu-id="b69e7-119">The phone number can be up to 17 digits and may be followed by an extension in the format ;ext= followed by the extension number.</span></span>

- <span data-ttu-id="b69e7-120">**Servizio annunci** Selezionare **annuncio** per gestire la chiamata in arrivo o la **messaggistica unificata** di Exchange per avere un operatore automatico di messaggistica unificata di Exchange per gestire la chiamata in arrivo.</span><span class="sxs-lookup"><span data-stu-id="b69e7-120">**Announcement service** Select **Announcement** to have the Announcement application handle the incoming call or **Exchange UM** to have an Exchange UM Auto Attendant handle the incoming call.</span></span>

- <span data-ttu-id="b69e7-121">Se è stato selezionato l' **annuncio** per il **servizio annunci**:</span><span class="sxs-lookup"><span data-stu-id="b69e7-121">If you selected **Announcement** for **Announcement service**:</span></span>

  - <span data-ttu-id="b69e7-122">**Nome di dominio completo del server di destinazione** Selezionare l'ID servizio del servizio applicazione che esegue l'applicazione di annuncio che gestirà le chiamate in arrivo in questo intervallo di numeri non assegnati.</span><span class="sxs-lookup"><span data-stu-id="b69e7-122">**FQDN of destination server** Select the service ID of the Application service that runs the Announcement application that will handle incoming calls to this range of unassigned numbers.</span></span>

  - <span data-ttu-id="b69e7-123">**Annuncio** Selezionare l'annuncio da riprodurre per l'intervallo di numeri non assegnati.</span><span class="sxs-lookup"><span data-stu-id="b69e7-123">**Announcement** Select the announcement to be played for this range of unassigned numbers.</span></span>

- <span data-ttu-id="b69e7-124">Se è stata selezionata la **messaggistica unificata di Exchange** per il **servizio annunci**:</span><span class="sxs-lookup"><span data-stu-id="b69e7-124">If you selected **Exchange UM** for **Announcement service**:</span></span>

  - <span data-ttu-id="b69e7-125">**Numero di telefono dell'operatore automatico** Selezionare il numero di telefono per l'operatore automatico di messaggistica unificata di Exchange.</span><span class="sxs-lookup"><span data-stu-id="b69e7-125">**Auto Attendant phone number** Select the phone number for the Exchange UM Auto Attendant.</span></span>

<span data-ttu-id="b69e7-126">Per informazioni dettagliate sulle caratteristiche e le funzionalità degli annunci, vedere [pianificare l'applicazione di annunci in Skype for Business 2015](../../plan-your-deployment/enterprise-voice-solution/announcement.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="b69e7-126">For details about Announcement features and capabilities, see [Plan for the Announcement application in Skype for Business 2015](../../plan-your-deployment/enterprise-voice-solution/announcement.md) in the Planning documentation.</span></span> <span data-ttu-id="b69e7-127">Per informazioni dettagliate sull'utilizzo di intervalli di numeri non assegnati, vedere [Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) nella documentazione relativa alle operazioni.</span><span class="sxs-lookup"><span data-stu-id="b69e7-127">For details about working with unassigned number ranges, see [Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) in the Operations documentation.</span></span>


