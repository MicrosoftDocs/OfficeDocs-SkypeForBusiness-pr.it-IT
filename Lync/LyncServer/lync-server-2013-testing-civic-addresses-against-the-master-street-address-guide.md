---
title: Test degli indirizzi civici nella Guida all'indirizzo Master Street
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
ms.openlocfilehash: 37d6aa1443dc2e062aa099237d9b25f2b33e32b2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745811"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-civic-addresses-against-the-master-street-address-guide-in-lync-server-2013"></a><span data-ttu-id="968df-102">Test degli indirizzi civici nella Guida all'indirizzo Master Street in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="968df-102">Testing civic addresses against the master street address guide in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="968df-103">_**Argomento Ultima modifica:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="968df-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="968df-104">Pianificazione della verifica</span><span class="sxs-lookup"><span data-stu-id="968df-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="968df-105">Quotidiana</span><span class="sxs-lookup"><span data-stu-id="968df-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="968df-106">Strumento di test</span><span class="sxs-lookup"><span data-stu-id="968df-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="968df-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="968df-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="968df-108">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="968df-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="968df-109">Quando si esegue localmente tramite Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="968df-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="968df-110">Quando si esegue usando un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga delle autorizzazioni per eseguire il cmdlet Test-CsRegistration.</span><span class="sxs-lookup"><span data-stu-id="968df-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsRegistration cmdlet.</span></span> <span data-ttu-id="968df-111">Per visualizzare un elenco di tutti i ruoli RBAC che possono usare questo cmdlet, eseguire il comando seguente dal prompt di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="968df-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLisCivicAddress &quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="968df-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="968df-112">Description</span></span>

<span data-ttu-id="968df-113">Il cmdlet Test-CsLisCivicAddress viene usato per verificare le posizioni aggiunte al database del servizio informazioni sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="968df-113">The Test-CsLisCivicAddress cmdlet is used to verify locations that were added to your Location Information service (LIS) database.</span></span> <span data-ttu-id="968df-114">Il cmdlet funziona confrontando le posizioni in base alle posizioni trovate nella Guida di indirizzi master Street (stradario) che appartiene al provider di routing di rete E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="968df-114">The cmdlet works by comparing locations against the locations found in the Master Street Address Guide (MSAG) that belongs to your E9-1-1 Network Routing Provider.</span></span> <span data-ttu-id="968df-115">Se non si dispone di un provider di routing di rete o se non è possibile raggiungere il provider, i test avranno esito negativo.</span><span class="sxs-lookup"><span data-stu-id="968df-115">If you do not have a network routing provider or if the provider cannot be reached, then your tests will fail.</span></span>

<span data-ttu-id="968df-116">Se si aggiunge il parametro facoltativo switch UpdateValidationStatus al comando, la proprietà del database MSAGValid corrispondente verrà impostata su true per ogni indirizzo che passa il test.</span><span class="sxs-lookup"><span data-stu-id="968df-116">If you add the optional switch parameter UpdateValidationStatus to your command, then the corresponding MSAGValid database property will be set to True for each address passing the test.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="968df-117">Eseguire il test</span><span class="sxs-lookup"><span data-stu-id="968df-117">Running the test</span></span>

<span data-ttu-id="968df-118">Il cmdlet Test-CsLisCivicAddress può essere usato per testare singoli indirizzi o per testare più indirizzi.</span><span class="sxs-lookup"><span data-stu-id="968df-118">The Test-CsLisCivicAddress cmdlet can be used to test individual addresses or to test multiple addresses.</span></span> <span data-ttu-id="968df-119">Ad esempio, questo comando verifica un singolo indirizzo situato in Redmond, WA:</span><span class="sxs-lookup"><span data-stu-id="968df-119">For example, this command tests a single address located in Redmond, WA:</span></span>

    Test-CsLisCivicAddress -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName Main -StreetSuffix St -PostDirectional "" -City Redmond -State WA -PostalCode 98052 -Country US -UpdateValidationStatus

<span data-ttu-id="968df-120">In base al confronto, questo comando verifica tutti gli indirizzi attualmente presenti nel database LIS:</span><span class="sxs-lookup"><span data-stu-id="968df-120">By comparison, this command tests all the addresses currently in your LIS database:</span></span>

    Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus

<span data-ttu-id="968df-121">Per altre informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsRegistration](https://technet.microsoft.com/en-us/library/Gg412737(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="968df-121">For more information, see the Help documentation for the [Test-CsRegistration](https://technet.microsoft.com/en-us/library/Gg412737(v=OCS.15)) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="968df-122">Determinare l'esito positivo o negativo</span><span class="sxs-lookup"><span data-stu-id="968df-122">Determining success or failure</span></span>

<span data-ttu-id="968df-123">Test-CsLisCivicAddress restituirà l'esito positivo o negativo degli indirizzi forniti.</span><span class="sxs-lookup"><span data-stu-id="968df-123">Test-CsLisCivicAddress will report back Success or Failure for the supplied addresses.</span></span> <span data-ttu-id="968df-124">Un test di indirizzo non riesce se non è possibile trovare l'indirizzo o se il provider di servizi non può essere contattato.</span><span class="sxs-lookup"><span data-stu-id="968df-124">An address test will fail if the address cannot be found or if the service provider cannot be contacted.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="968df-125">Motivi per cui il test potrebbe non essere riuscito</span><span class="sxs-lookup"><span data-stu-id="968df-125">Reasons why the test might have failed</span></span>

<span data-ttu-id="968df-126">Ecco alcuni motivi comuni per cui Test-CsLisCivicAddress potrebbe non riuscire:</span><span class="sxs-lookup"><span data-stu-id="968df-126">Here are some common reasons why Test-CsLisCivicAddress might fail:</span></span>

  - <span data-ttu-id="968df-127">Il provider di servizi LIS potrebbe non essere disponibile.</span><span class="sxs-lookup"><span data-stu-id="968df-127">The LIS service provider might not be available.</span></span> <span data-ttu-id="968df-128">Puoi recuperare l'URL del provider di servizi LIS eseguendo il cmdlet Get-CsLisConfiguration:</span><span class="sxs-lookup"><span data-stu-id="968df-128">You can retrieve the URL of your LIS service provider by running the Get-CsLisConfiguration cmdlet:</span></span>
    
        Get-CsLisConfiguration 
    
    <span data-ttu-id="968df-129">Puoi quindi eseguire il ping dell'URL per verificare che il provider di servizi sia disponibile.</span><span class="sxs-lookup"><span data-stu-id="968df-129">You can then ping that URL to verify that the service provider is available.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

