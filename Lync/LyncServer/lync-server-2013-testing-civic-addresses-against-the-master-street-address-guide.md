---
title: Verifica degli indirizzi civici rispetto alla guida all'indirizzo Master Street
description: Verifica degli indirizzi civici rispetto alla guida all'indirizzo Master Street.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing civic addresses against the master street address guide
ms:assetid: dc680de9-2a0f-4fd3-a99e-9bab0bc30ae5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690132(v=OCS.15)
ms:contentKeyID: 63969657
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 16e0d721b70e3db175b2d23ddee6f59d13a13c4e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560702"
---
# <a name="testing-civic-addresses-against-the-master-street-address-guide-in-lync-server-2013"></a><span data-ttu-id="be276-103">Verifica degli indirizzi civici in base alla guida all'indirizzo Master Street in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="be276-103">Testing civic addresses against the master street address guide in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="be276-104">_**Ultimo argomento modificato:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="be276-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="be276-105">Pianificazione della verifica</span><span class="sxs-lookup"><span data-stu-id="be276-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="be276-106">Giornaliero</span><span class="sxs-lookup"><span data-stu-id="be276-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="be276-107">Strumento di testing</span><span class="sxs-lookup"><span data-stu-id="be276-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="be276-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="be276-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="be276-109">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="be276-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="be276-110">Quando si esegue localmente utilizzando Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="be276-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="be276-111">Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet Test-CsRegistration.</span><span class="sxs-lookup"><span data-stu-id="be276-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsRegistration cmdlet.</span></span> <span data-ttu-id="be276-112">Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="be276-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLisCivicAddress &quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="be276-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="be276-113">Description</span></span>

<span data-ttu-id="be276-114">Il cmdlet Test-CsLisCivicAddress viene utilizzato per verificare i percorsi che sono stati aggiunti al database del servizio informazioni percorso (LIS, Location Information Service).</span><span class="sxs-lookup"><span data-stu-id="be276-114">The Test-CsLisCivicAddress cmdlet is used to verify locations that were added to your Location Information service (LIS) database.</span></span> <span data-ttu-id="be276-115">Il cmdlet funziona confrontando i percorsi con i percorsi trovati nella Master Street Address Guide (allo stradario generale) che appartiene al provider di routing di rete di E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="be276-115">The cmdlet works by comparing locations against the locations found in the Master Street Address Guide (MSAG) that belongs to your E9-1-1 Network Routing Provider.</span></span> <span data-ttu-id="be276-116">Se non si dispone di un provider di routing di rete o se non è possibile raggiungere il provider, i test avranno esito negativo.</span><span class="sxs-lookup"><span data-stu-id="be276-116">If you do not have a network routing provider or if the provider cannot be reached, then your tests will fail.</span></span>

<span data-ttu-id="be276-117">Se si aggiunge il parametro facoltativo switch UpdateValidationStatus al comando, la proprietà corrispondente di database di MSAGValid verrà impostata su true per ogni indirizzo che passa il test.</span><span class="sxs-lookup"><span data-stu-id="be276-117">If you add the optional switch parameter UpdateValidationStatus to your command, then the corresponding MSAGValid database property will be set to True for each address passing the test.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="be276-118">Esecuzione del test</span><span class="sxs-lookup"><span data-stu-id="be276-118">Running the test</span></span>

<span data-ttu-id="be276-119">Il cmdlet Test-CsLisCivicAddress può essere utilizzato per testare singoli indirizzi o per testare più indirizzi.</span><span class="sxs-lookup"><span data-stu-id="be276-119">The Test-CsLisCivicAddress cmdlet can be used to test individual addresses or to test multiple addresses.</span></span> <span data-ttu-id="be276-120">Ad esempio, questo comando consente di testare un singolo indirizzo che si trova a Redmond, WA:</span><span class="sxs-lookup"><span data-stu-id="be276-120">For example, this command tests a single address located in Redmond, WA:</span></span>

    Test-CsLisCivicAddress -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName Main -StreetSuffix St -PostDirectional "" -City Redmond -State WA -PostalCode 98052 -Country US -UpdateValidationStatus

<span data-ttu-id="be276-121">In base al confronto, questo comando verifica tutti gli indirizzi attualmente presenti nel database LIS:</span><span class="sxs-lookup"><span data-stu-id="be276-121">By comparison, this command tests all the addresses currently in your LIS database:</span></span>

    Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus

<span data-ttu-id="be276-122">Per ulteriori informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsRegistration](https://technet.microsoft.com/library/Gg412737(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="be276-122">For more information, see the Help documentation for the [Test-CsRegistration](https://technet.microsoft.com/library/Gg412737(v=OCS.15)) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="be276-123">Determinazione dell'esito positivo o negativo</span><span class="sxs-lookup"><span data-stu-id="be276-123">Determining success or failure</span></span>

<span data-ttu-id="be276-124">Test-CsLisCivicAddress riporterà l'esito positivo o negativo degli indirizzi forniti.</span><span class="sxs-lookup"><span data-stu-id="be276-124">Test-CsLisCivicAddress will report back Success or Failure for the supplied addresses.</span></span> <span data-ttu-id="be276-125">Un test degli indirizzi avrà esito negativo se non è possibile trovare l'indirizzo o se non è possibile contattare il provider di servizi.</span><span class="sxs-lookup"><span data-stu-id="be276-125">An address test will fail if the address cannot be found or if the service provider cannot be contacted.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="be276-126">Motivi per cui il test potrebbe non avere avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="be276-126">Reasons why the test might have failed</span></span>

<span data-ttu-id="be276-127">Di seguito sono riportate alcune ragioni comuni per cui Test-CsLisCivicAddress potrebbero non riuscire:</span><span class="sxs-lookup"><span data-stu-id="be276-127">Here are some common reasons why Test-CsLisCivicAddress might fail:</span></span>

  - <span data-ttu-id="be276-128">Il provider di servizi LIS potrebbe non essere disponibile.</span><span class="sxs-lookup"><span data-stu-id="be276-128">The LIS service provider might not be available.</span></span> <span data-ttu-id="be276-129">È possibile recuperare l'URL del provider di servizi LIS eseguendo il cmdlet Get-CsLisConfiguration:</span><span class="sxs-lookup"><span data-stu-id="be276-129">You can retrieve the URL of your LIS service provider by running the Get-CsLisConfiguration cmdlet:</span></span>
    
        Get-CsLisConfiguration 
    
    <span data-ttu-id="be276-130">È quindi possibile eseguire il ping dell'URL per verificare che il provider di servizi sia disponibile.</span><span class="sxs-lookup"><span data-stu-id="be276-130">You can then ping that URL to verify that the service provider is available.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

