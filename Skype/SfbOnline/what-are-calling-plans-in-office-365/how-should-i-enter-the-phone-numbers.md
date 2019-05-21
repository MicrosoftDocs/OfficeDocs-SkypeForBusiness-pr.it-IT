---
title: Come è possibile immettere i numeri di telefono?
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 28aa24b4-8c81-4327-9752-989ea7540db2
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords: ms.lync.lac.PortOrderNumbers
ms.custom:
- Calling Plans
description: 'Scopri come configurare i numeri di telefono quando li porti in Skype for business. '
ms.openlocfilehash: df9d82a6e785954a95a455f0e43aa0e077f40bcf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280531"
---
# <a name="how-should-i-enter-the-phone-numbers"></a><span data-ttu-id="6903a-103">Come è possibile immettere i numeri di telefono?</span><span class="sxs-lookup"><span data-stu-id="6903a-103">How should I enter the phone numbers?</span></span>

<span data-ttu-id="6903a-104">Quando si trasferiscono i numeri di telefono, è necessario immetterli nel formato corretto.</span><span class="sxs-lookup"><span data-stu-id="6903a-104">When you are porting phone numbers, you must enter them in the correct format.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="6903a-105">Ogni numero di telefono o intervallo di numeri di telefono deve essere immesso separatamente per ogni riga.</span><span class="sxs-lookup"><span data-stu-id="6903a-105">Each phone number or range of phone number must be entered separately on each line.</span></span> 
  
- <span data-ttu-id="6903a-106">Quando si immette un singolo numero di telefono:</span><span class="sxs-lookup"><span data-stu-id="6903a-106">When you are entering single phone numbers:</span></span>
    
  - <span data-ttu-id="6903a-107">Tutti i caratteri speciali verranno ignorati (incluso Dash "-").</span><span class="sxs-lookup"><span data-stu-id="6903a-107">All special characters will be ignored (including dash "-").</span></span> <span data-ttu-id="6903a-108">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="6903a-108">For example:</span></span>
    
  - <span data-ttu-id="6903a-109">Per un numero a 10 cifre: \*\* &amp; \*(425\*() (\*&amp;4&amp;\*()) (\*250649\*\* verrà corretto in **+ 14255550649**.</span><span class="sxs-lookup"><span data-stu-id="6903a-109">For a 10-digit number: **&amp;\*(425\*()(\*&amp;4&amp;\*())(\*250649** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="6903a-110">Per un numero a 11 cifre: **1\*() (\*&amp;42&amp;\*()\*&amp;(55550649** verrà corretto in **+ 14255550649**.</span><span class="sxs-lookup"><span data-stu-id="6903a-110">For an 11-digit number: **1\*()(\*&amp;42&amp;\*()(\*&amp;55550649** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="6903a-111">Tutti i tag verranno ignorati se sono presenti 10 o 11 cifre.</span><span class="sxs-lookup"><span data-stu-id="6903a-111">All tags will be ignored if there are 10 or 11 digits.</span></span> <span data-ttu-id="6903a-112">Ad esempio, \*\* \<div> 4255551234\</div>\*\* sarà **+ 14255551234**.</span><span class="sxs-lookup"><span data-stu-id="6903a-112">For example, **\<div> 4255551234\</div>** will be **+14255551234**.</span></span>
    
  - <span data-ttu-id="6903a-113">"-", spazio e parentesi verranno ignorati.</span><span class="sxs-lookup"><span data-stu-id="6903a-113">"-", space, and parenthesis will be ignored.</span></span> <span data-ttu-id="6903a-114">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="6903a-114">For example:</span></span>
    
  - <span data-ttu-id="6903a-115">Per un numero a 10 cifre: **(425) 555-6776** verrà corretto in **+ 14255556776**.</span><span class="sxs-lookup"><span data-stu-id="6903a-115">For a 10-digit number: **(425) 555-6776** will be corrected to **+14255556776**.</span></span>
    
  - <span data-ttu-id="6903a-116">Per un numero a 11 cifre: **1 (425) 555-6776** verrà corretto in **+ 14255556776**.</span><span class="sxs-lookup"><span data-stu-id="6903a-116">For an 11-digit number: **1(425) 555-6776** will be corrected to **+14255556776**.</span></span>
    
  - <span data-ttu-id="6903a-117">Tutte le lettere verranno trattate come caratteri speciali e ignorate se è presente un numero di telefono di 10 cifre o di 11 numeri.</span><span class="sxs-lookup"><span data-stu-id="6903a-117">All letters will be treated as special characters and ignored if there is a 10-digit or 11-digit phone number.</span></span> <span data-ttu-id="6903a-118">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="6903a-118">For example:</span></span>
    
  - <span data-ttu-id="6903a-119">Per un numero a 10 cifre: **14jaosia2reoij05jof55506ajfoj49isdjf** verrà corretto in **+ 14255550649**.</span><span class="sxs-lookup"><span data-stu-id="6903a-119">For a 10-digit number: **14jaosia2reoij05jof55506ajfoj49isdjf** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="6903a-120">Per un numero a 11 cifre: **1ade4jaoda2rfoij05ojof55506dsfoj49if** verrà corretto in **+ 14255550649**.</span><span class="sxs-lookup"><span data-stu-id="6903a-120">For an 11-digit number: **1ade4jaoda2rfoij05ojof55506dsfoj49if** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="6903a-121">Qualsiasi combinazione di caratteri speciali, anche in altre lingue, verrà corretta.</span><span class="sxs-lookup"><span data-stu-id="6903a-121">Any combination of special characters, even in other languages, will be corrected.</span></span> <span data-ttu-id="6903a-122">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="6903a-122">For example:</span></span> 
    
  - <span data-ttu-id="6903a-123">Per un numero a 10 cifre:**中文 4 中文2ajj5\*() (\*(5 ()... 551345** verrà corretto in **+ 14555551345**.</span><span class="sxs-lookup"><span data-stu-id="6903a-123">For a 10-digit number: **中文4中文2ajj5\*（）（\*（5()...551345** will be corrected to **+14555551345**.</span></span>
    
  - <span data-ttu-id="6903a-124">Per un numero a 11 cifre:**中文 4 中文 2 $ a5\*() (\*(5 ()... 55 (. 1345** verrà corretto in **+ 14555551345**.</span><span class="sxs-lookup"><span data-stu-id="6903a-124">For an 11-digit number: **中文4中文2$a5\*（）（\*（5()...55(.1345** will be corrected to **+14555551345**.</span></span>
    
  - <span data-ttu-id="6903a-125">Se i numeri contengono meno di 10 cifre o più di 11 cifre, verranno evidenziati per correggere l'utente:</span><span class="sxs-lookup"><span data-stu-id="6903a-125">If any numbers contain fewer than 10 digits or more than 11 digits, they will be highlighted for the user to correct:</span></span>
    
  - <span data-ttu-id="6903a-126">\*\*5551245\* \* sarà evidenziato e deve essere corretto.</span><span class="sxs-lookup"><span data-stu-id="6903a-126">\*\*5551245\*\* will be highlighted and need to be corrected.</span></span>
    
  - <span data-ttu-id="6903a-127">**1234567891011** sarà evidenziato e deve essere corretto.</span><span class="sxs-lookup"><span data-stu-id="6903a-127">**1234567891011** will be highlighted and need to be corrected.</span></span>
    
  - <span data-ttu-id="6903a-128">Tutti i numeri con meno di 10 cifre o più di 11 cifre, con eventuali caratteri speciali, verranno evidenziati senza essere corretti automaticamente.</span><span class="sxs-lookup"><span data-stu-id="6903a-128">Any numbers that are fewer than 10 digits or more than 11 digits, with any special characters, will be highlighted without being automatically corrected.</span></span>
    
  - <span data-ttu-id="6903a-129">Per un numero a 7 cifre senza caratteri speciali immessi: **123456abcdefg7** verrà evidenziato e deve essere corretto, ma le lettere non verranno ignorate.</span><span class="sxs-lookup"><span data-stu-id="6903a-129">For a 7-digit number without special characters that is entered: **123456abcdefg7** will be highlighted and need to be corrected, but the letters won't be ignored.</span></span>
    
  - <span data-ttu-id="6903a-130">Per un numero a 7 cifre con caratteri speciali immessi: **12345! @ # $% ^&amp;\*()--@ # $% ^&amp;\*() 7** verrà evidenziato per essere corretto.</span><span class="sxs-lookup"><span data-stu-id="6903a-130">For a 7-digit number with special characters that is entered: **12345!@#$%^&amp;\*()--@#$%^&amp;\*()7** will be highlighted to be corrected.</span></span> <span data-ttu-id="6903a-131">I caratteri speciali non verranno ignorati.</span><span class="sxs-lookup"><span data-stu-id="6903a-131">The special characters won't be ignored.</span></span>
    
- <span data-ttu-id="6903a-132">Quando si immette un intervallo di numeri di telefono.</span><span class="sxs-lookup"><span data-stu-id="6903a-132">When you are entering a range of phone numbers.</span></span>
    
  - <span data-ttu-id="6903a-133">Sono consentiti solo due numeri di telefono.</span><span class="sxs-lookup"><span data-stu-id="6903a-133">Only two phone numbers are allowed.</span></span> <span data-ttu-id="6903a-134">Il numero più piccolo deve essere il primo numero nell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="6903a-134">The smaller number must be the first number in the range.</span></span>
    
  - <span data-ttu-id="6903a-135">Tutti i caratteri speciali (ad eccezione del trattino "-") vengono trattati come numeri singoli.</span><span class="sxs-lookup"><span data-stu-id="6903a-135">All special characters (except for the dash "-") are treated the same as single numbers.</span></span> <span data-ttu-id="6903a-136">Ad esempio, **(425) 555 0&amp;\*(123-(1425) 5557899nm** verrà corretto in **+ 14255550123-+ 13202040659**.</span><span class="sxs-lookup"><span data-stu-id="6903a-136">For example, **(425)555 0&amp;\*(123-(1425)5557899nm** will be corrected to **+14255550123 -+13202040659**.</span></span>
    
  - <span data-ttu-id="6903a-137">"-" Viene usato solo per separare i due numeri.</span><span class="sxs-lookup"><span data-stu-id="6903a-137">The "-" is used for only separating the two numbers.</span></span> <span data-ttu-id="6903a-138">Non è supportata l'inclusione di più "-" nell'intervallo di numeri.</span><span class="sxs-lookup"><span data-stu-id="6903a-138">It isn't supported to include multiple "-" in the number range.</span></span> <span data-ttu-id="6903a-139">Ad esempio, **(425) 555-0649-(425) 555-1115** deve essere immesso come **(425) 5550649-(425) 5551115**.</span><span class="sxs-lookup"><span data-stu-id="6903a-139">For example, **(425) 555-0649 - (425) 555-1115** should be entered as **(425) 5550649 - (425) 5551115**.</span></span>
    
  <span data-ttu-id="6903a-140">**Per istruzioni dettagliate, vedere [trasferire i numeri di telefono in Office 365](/microsoftteams/transfer-phone-numbers-to-office-365).**</span><span class="sxs-lookup"><span data-stu-id="6903a-140">**For complete step-by-step instructions, see [Transfer phone numbers to Office 365](/microsoftteams/transfer-phone-numbers-to-office-365).**</span></span>

  > [!NOTE]
  > <span data-ttu-id="6903a-141">Se hai bisogno di ulteriori numeri di telefono, visita la pagina [Contattare il supporto per i prodotti aziendali - Guida per gli amministratori](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span><span class="sxs-lookup"><span data-stu-id="6903a-141">If you need to get more telephone numbers than this, please [contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)</span></span>

  
## <a name="related-topics"></a><span data-ttu-id="6903a-142">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="6903a-142">Related topics</span></span>
[<span data-ttu-id="6903a-143">Domande comuni sul trasferimento dei numeri di telefono</span><span class="sxs-lookup"><span data-stu-id="6903a-143">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="6903a-144">Diversi tipi di numeri di telefono utilizzati nei Piani per chiamate</span><span class="sxs-lookup"><span data-stu-id="6903a-144">Different kinds of phone numbers used for Calling Plans</span></span>](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="6903a-145">Gestire i numeri di telefono per la propria organizzazione</span><span class="sxs-lookup"><span data-stu-id="6903a-145">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="6903a-146">Termini e condizioni per le chiamate al numero di emergenza</span><span class="sxs-lookup"><span data-stu-id="6903a-146">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="6903a-147">[Skype for Business Online: dichiarazione di non responsabilità per le chiamate di emergenza](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="6903a-147">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 