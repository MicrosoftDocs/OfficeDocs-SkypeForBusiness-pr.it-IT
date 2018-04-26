---
title: Come è necessario immettere i numeri di telefono?
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 28aa24b4-8c81-4327-9752-989ea7540db2
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords: ms.lync.lac.PortOrderNumbers
ms.custom:
- Calling Plans
description: 'Informazioni su come configurare i numeri di telefono quando porta Skype per le aziende. '
ms.openlocfilehash: 74914b98ccc60984f1d2be16f6a3351e7b26b2cf
ms.sourcegitcommit: f942232d43fc4ad56b34dd400fdb4bca39013f5f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="how-should-i-enter-the-phone-numbers"></a><span data-ttu-id="88b0d-103">Come è necessario immettere i numeri di telefono?</span><span class="sxs-lookup"><span data-stu-id="88b0d-103">How should I enter the phone numbers?</span></span>

<span data-ttu-id="88b0d-104">Quando si trasferisce i numeri di telefono, è necessario immettere tali nel formato corretto.</span><span class="sxs-lookup"><span data-stu-id="88b0d-104">When you are porting phone numbers, you must enter them in the correct format.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="88b0d-105">Ogni numero di telefono o un intervallo di numero di telefono deve essere immesso separatamente su ogni riga.</span><span class="sxs-lookup"><span data-stu-id="88b0d-105">Each phone number or range of phone number must be entered separately on each line.</span></span> 
  
- <span data-ttu-id="88b0d-106">Quando si immettono i numeri di telefono singolo:</span><span class="sxs-lookup"><span data-stu-id="88b0d-106">When you are entering single phone numbers:</span></span>
    
  - <span data-ttu-id="88b0d-107">Verranno ignorati tutti i caratteri speciali (inclusi trattino "-").</span><span class="sxs-lookup"><span data-stu-id="88b0d-107">All special characters will be ignored (including dash "-").</span></span> <span data-ttu-id="88b0d-108">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="88b0d-108">For example:</span></span>
    
  - <span data-ttu-id="88b0d-109">Per un numero a 10 cifre: \*\* &amp; \*(425\*() (\*&amp;4&amp;\*()) (\*250649\*\* verrà corretto per **+14255550649**.</span><span class="sxs-lookup"><span data-stu-id="88b0d-109">For a 10-digit number: **&amp;\*(425\*()(\*&amp;4&amp;\*())(\*250649** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="88b0d-110">Per un numero a 11 cifre: **1\*() (\*&amp;42&amp;\*() (\*&amp;55550649** verrà corretto per **+14255550649**.</span><span class="sxs-lookup"><span data-stu-id="88b0d-110">For an 11-digit number: **1\*()(\*&amp;42&amp;\*()(\*&amp;55550649** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="88b0d-111">Tutti i tag verranno ignorati se sono presenti 10 o 11 cifre.</span><span class="sxs-lookup"><span data-stu-id="88b0d-111">All tags will be ignored if there are 10 or 11 digits.</span></span> <span data-ttu-id="88b0d-112">Ad esempio ** \<div > 4255551234\</div >** sarà **+ 14255551234**.</span><span class="sxs-lookup"><span data-stu-id="88b0d-112">For example, **\<div> 4255551234\</div>** will be **+14255551234**.</span></span>
    
  - <span data-ttu-id="88b0d-113">"-", verrà ignorato spazio e parentesi chiusa.</span><span class="sxs-lookup"><span data-stu-id="88b0d-113">"-", space, and parenthesis will be ignored.</span></span> <span data-ttu-id="88b0d-114">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="88b0d-114">For example:</span></span>
    
  - <span data-ttu-id="88b0d-115">Per un numero a 10 cifre: **(425) 555-6776** verrà corretto per **+14255556776**.</span><span class="sxs-lookup"><span data-stu-id="88b0d-115">For a 10-digit number: **(425) 555-6776** will be corrected to **+14255556776**.</span></span>
    
  - <span data-ttu-id="88b0d-116">Per un numero a 11 cifre: **555-6776 1(425)** verrà corretto per **+14255556776**.</span><span class="sxs-lookup"><span data-stu-id="88b0d-116">For an 11-digit number: **1(425) 555-6776** will be corrected to **+14255556776**.</span></span>
    
  - <span data-ttu-id="88b0d-117">Tutte le lettere verranno considerate come caratteri speciali e viene ignorate se esiste un numero di telefono 10 o 11 cifre.</span><span class="sxs-lookup"><span data-stu-id="88b0d-117">All letters will be treated as special characters and ignored if there is a 10-digit or 11-digit phone number.</span></span> <span data-ttu-id="88b0d-118">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="88b0d-118">For example:</span></span>
    
  - <span data-ttu-id="88b0d-119">Per un numero a 10 cifre: **14jaosia2reoij05jof55506ajfoj49isdjf** verrà corretto per **+14255550649**.</span><span class="sxs-lookup"><span data-stu-id="88b0d-119">For a 10-digit number: **14jaosia2reoij05jof55506ajfoj49isdjf** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="88b0d-120">Per un numero a 11 cifre: **1ade4jaoda2rfoij05ojof55506dsfoj49if** verrà corretto per **+14255550649**.</span><span class="sxs-lookup"><span data-stu-id="88b0d-120">For an 11-digit number: **1ade4jaoda2rfoij05ojof55506dsfoj49if** will be corrected to **+14255550649**.</span></span>
    
  - <span data-ttu-id="88b0d-121">Verrà corretto qualsiasi combinazione dei caratteri speciali, anche in altre lingue.</span><span class="sxs-lookup"><span data-stu-id="88b0d-121">Any combination of special characters, even in other languages, will be corrected.</span></span> <span data-ttu-id="88b0d-122">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="88b0d-122">For example:</span></span> 
    
  - <span data-ttu-id="88b0d-123">Per un numero a 10 cifre:**中文4中文2ajj5\*() (\*(5() 551345** verrà corretto per **+14555551345**.</span><span class="sxs-lookup"><span data-stu-id="88b0d-123">For a 10-digit number: **中文4中文2ajj5\*（）（\*（5()...551345** will be corrected to **+14555551345**.</span></span>
    
  - <span data-ttu-id="88b0d-124">Per un numero a 11 cifre:**中文4中文2$ a5\*() (\*(5() 55 (.1345** verrà corretto per **+14555551345**.</span><span class="sxs-lookup"><span data-stu-id="88b0d-124">For an 11-digit number: **中文4中文2$a5\*（）（\*（5()...55(.1345** will be corrected to **+14555551345**.</span></span>
    
  - <span data-ttu-id="88b0d-125">Se tutti i numeri contengono meno di 10 o superiore a 11 cifre, vengono evidenziate per l'utente corretta:</span><span class="sxs-lookup"><span data-stu-id="88b0d-125">If any numbers contain fewer than 10 digits or more than 11 digits, they will be highlighted for the user to correct:</span></span>
    
  - <span data-ttu-id="88b0d-126">\*\*5551245\* \* verrà evidenziata e da correggere.</span><span class="sxs-lookup"><span data-stu-id="88b0d-126">\*\*5551245\*\* will be highlighted and need to be corrected.</span></span>
    
  - <span data-ttu-id="88b0d-127">**1234567891011** verrà evidenziata e da correggere.</span><span class="sxs-lookup"><span data-stu-id="88b0d-127">**1234567891011** will be highlighted and need to be corrected.</span></span>
    
  - <span data-ttu-id="88b0d-128">Tutti i numeri presenti meno di 10 o superiore a 11 cifre, con i caratteri speciali, verranno evidenziati senza da correggere automaticamente.</span><span class="sxs-lookup"><span data-stu-id="88b0d-128">Any numbers that are fewer than 10 digits or more than 11 digits, with any special characters, will be highlighted without being automatically corrected.</span></span>
    
  - <span data-ttu-id="88b0d-129">Per un numero a 7 cifre senza caratteri speciali immessi: **123456abcdefg7** verrà evidenziata e da correggere, ma non verranno ignorate le lettere.</span><span class="sxs-lookup"><span data-stu-id="88b0d-129">For a 7-digit number without special characters that is entered: **123456abcdefg7** will be highlighted and need to be corrected, but the letters won't be ignored.</span></span>
    
  - <span data-ttu-id="88b0d-130">Per un numero a 7 cifre con caratteri speciali immessi: **12345!@#$%^&amp;\*(.)-@# $% ^&amp;\*(7)** verrà evidenziata per da correggere.</span><span class="sxs-lookup"><span data-stu-id="88b0d-130">For a 7-digit number with special characters that is entered: **12345!@#$%^&amp;\*()--@#$%^&amp;\*()7** will be highlighted to be corrected.</span></span> <span data-ttu-id="88b0d-131">I caratteri speciali non vengono ignorati.</span><span class="sxs-lookup"><span data-stu-id="88b0d-131">The special characters won't be ignored.</span></span>
    
- <span data-ttu-id="88b0d-132">Quando si immette un intervallo di numeri di telefono.</span><span class="sxs-lookup"><span data-stu-id="88b0d-132">When you are entering a range of phone numbers.</span></span>
    
  - <span data-ttu-id="88b0d-133">Sono consentiti solo due numeri di telefono.</span><span class="sxs-lookup"><span data-stu-id="88b0d-133">Only two phone numbers are allowed.</span></span> <span data-ttu-id="88b0d-134">Il numero più piccolo deve essere il primo numero nell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="88b0d-134">The smaller number must be the first number in the range.</span></span>
    
  - <span data-ttu-id="88b0d-135">Tutti i caratteri speciali (tranne per il trattino "-") vengono trattati come numeri singolo.</span><span class="sxs-lookup"><span data-stu-id="88b0d-135">All special characters (except for the dash "-") are treated the same as single numbers.</span></span> <span data-ttu-id="88b0d-136">Ad esempio, **(425) 555 0&amp;\*(123-(1425) 5557899nm** verrà corretto per **+ 14255550123 - +13202040659**.</span><span class="sxs-lookup"><span data-stu-id="88b0d-136">For example, **(425)555 0&amp;\*(123-(1425)5557899nm** will be corrected to **+14255550123 -+13202040659**.</span></span>
    
  - <span data-ttu-id="88b0d-137">Il "-" viene utilizzato per separare solo due numeri.</span><span class="sxs-lookup"><span data-stu-id="88b0d-137">The "-" is used for only separating the two numbers.</span></span> <span data-ttu-id="88b0d-138">Non è supportato in modo da includere più "-" nell'intervallo di numeri.</span><span class="sxs-lookup"><span data-stu-id="88b0d-138">It isn't supported to include multiple "-" in the number range.</span></span> <span data-ttu-id="88b0d-139">Ad esempio, **(425) 555-0649-(425) 555-1115** deve essere immesso come **(425) 5550649 - (425) 5551115**.</span><span class="sxs-lookup"><span data-stu-id="88b0d-139">For example, **(425) 555-0649 - (425) 555-1115** should be entered as **(425) 5550649 - (425) 5551115**.</span></span>
    
 <span data-ttu-id="88b0d-140">**Per istruzioni dettagliate complete, vedere [trasferire i numeri di telefono a Office 365](transfer-phone-numbers-to-office-365.md).**</span><span class="sxs-lookup"><span data-stu-id="88b0d-140">**For complete step-by-step instructions, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).**</span></span>

 > [!NOTE]
> <span data-ttu-id="88b0d-141">Se hai bisogno di ulteriori numeri di telefono, visita la pagina [Contattare il supporto per i prodotti aziendali - Guida per gli amministratori](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span><span class="sxs-lookup"><span data-stu-id="88b0d-141">If you need to get more telephone numbers than this, please [contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)</span></span>

  
## <a name="related-topics"></a><span data-ttu-id="88b0d-142">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="88b0d-142">Related topics</span></span>
[<span data-ttu-id="88b0d-143">Domande comuni sul trasferimento dei numeri di telefono</span><span class="sxs-lookup"><span data-stu-id="88b0d-143">Transferring phone numbers common questions</span></span>](transferring-phone-numbers-common-questions.md)

[<span data-ttu-id="88b0d-144">Diversi tipi di numeri di telefono utilizzati nei Piani per chiamate</span><span class="sxs-lookup"><span data-stu-id="88b0d-144">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="88b0d-145">Gestire i numeri di telefono per la propria organizzazione</span><span class="sxs-lookup"><span data-stu-id="88b0d-145">Manage phone numbers for your organization</span></span>](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[<span data-ttu-id="88b0d-146">Termini e condizioni per le chiamate al numero di emergenza</span><span class="sxs-lookup"><span data-stu-id="88b0d-146">Emergency calling terms and conditions</span></span>](../legal-and-regulatory/emergency-calling-terms-and-conditions.md)

<span data-ttu-id="88b0d-147">[Skype for Business Online: dichiarazione di non responsabilità per le chiamate di emergenza](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="88b0d-147">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 