---
title: 'Lync Server 2013: verificare i certificati server di Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Check server certificates
ms:assetid: 7b0474e8-0efe-47f0-84eb-a1ba575dabfd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725210(v=OCS.15)
ms:contentKeyID: 63969620
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dced86c93b7ec35cb410601f1d72720e25d156b0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981933"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="check-lync-server-2013-server-certificates"></a><span data-ttu-id="92f8c-102">Verificare i certificati server di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="92f8c-102">Check Lync Server 2013 server certificates</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="92f8c-103">_**Argomento Ultima modifica:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="92f8c-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="92f8c-104">Pianificazione della verifica</span><span class="sxs-lookup"><span data-stu-id="92f8c-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="92f8c-105">Mensile</span><span class="sxs-lookup"><span data-stu-id="92f8c-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="92f8c-106">Strumento di test</span><span class="sxs-lookup"><span data-stu-id="92f8c-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="92f8c-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="92f8c-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="92f8c-108">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="92f8c-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="92f8c-109">Quando si esegue localmente tramite Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="92f8c-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="92f8c-110">Quando si esegue usando un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga delle autorizzazioni per eseguire il cmdlet Get-CsCertificate.</span><span class="sxs-lookup"><span data-stu-id="92f8c-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Get-CsCertificate cmdlet.</span></span> <span data-ttu-id="92f8c-111">Per visualizzare un elenco di tutti i ruoli RBAC che possono usare questo cmdlet, eseguire il comando seguente dal prompt di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="92f8c-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Get-CsCertificate&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="92f8c-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="92f8c-112">Description</span></span>

<span data-ttu-id="92f8c-113">Il cmdlet Get-CsCertificate consente di recuperare informazioni su ognuno dei certificati di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="92f8c-113">The Get-CsCertificate cmdlet enables you to retrieve information about each of your Lync Server certificates.</span></span> <span data-ttu-id="92f8c-114">Questo è particolarmente importante perché i certificati hanno una data di scadenza predefinita.</span><span class="sxs-lookup"><span data-stu-id="92f8c-114">That’s especially important because certificates have a built-in expiration date.</span></span> <span data-ttu-id="92f8c-115">Ad esempio, i certificati emessi in privato scadono in genere dopo 12 mesi.</span><span class="sxs-lookup"><span data-stu-id="92f8c-115">For example,, privately-issued certificates typically expire after 12 months.</span></span> <span data-ttu-id="92f8c-116">Se uno dei certificati di Lync Server scade, si perderà la funzionalità associata finché il certificato non viene rinnovato o sostituito.</span><span class="sxs-lookup"><span data-stu-id="92f8c-116">If any of your Lync Server certificates expire then you'll lose the accompanying functionality until that certificate is renewed or replaced.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="92f8c-117">Eseguire il test</span><span class="sxs-lookup"><span data-stu-id="92f8c-117">Running the test</span></span>

<span data-ttu-id="92f8c-118">Per restituire informazioni su ognuno dei certificati di Lync Server è sufficiente eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="92f8c-118">To return information about each of your Lync Server certificates just run the following command:</span></span>

`Get-CsCertificate`

<span data-ttu-id="92f8c-119">In alternativa, è possibile filtrare le informazioni sul certificato restituito in base alla data di scadenza.</span><span class="sxs-lookup"><span data-stu-id="92f8c-119">Or, you can filter the return certificate information based on expiration date.</span></span> <span data-ttu-id="92f8c-120">Ad esempio, questo comando limita i dati restituiti ai certificati che scadono (non può essere usato dopo) il 1 giugno 2014:</span><span class="sxs-lookup"><span data-stu-id="92f8c-120">For example, this command limits the returned data to certificates that expire (cannot be used after) June 1, 2014:</span></span>

`Get-CsCertificate | Where-Object {$_.NotAfter -lt "6/1/2014"}`

<span data-ttu-id="92f8c-121">Per altre informazioni, vedere la documentazione della Guida relativa al cmdlet Get-CsCertificate.</span><span class="sxs-lookup"><span data-stu-id="92f8c-121">For more information, see the Help documentation for the Get-CsCertificate cmdlet.</span></span>

<span data-ttu-id="92f8c-122">Tieni presente che, anche se il cmdlet Test-CsCertificateConfiguration esiste, non è molto utile per gli amministratori.</span><span class="sxs-lookup"><span data-stu-id="92f8c-122">Note that, although the Test-CsCertificateConfiguration cmdlet exists, it is not very useful to administrators.</span></span> <span data-ttu-id="92f8c-123">Il cmdlet viene invece usato principalmente dalla creazione guidata certificato. Anche se il cmdlet funziona, le informazioni restituite sono di valore minimo, come illustrato nell'esempio di output seguente:</span><span class="sxs-lookup"><span data-stu-id="92f8c-123">(Instead, that cmdlet is primarily used by the Certificate wizard.) Although the cmdlet works, the information that it returns is of minimal value as shown in the following output example:</span></span>

<span data-ttu-id="92f8c-124">Uso di identificazione personale</span><span class="sxs-lookup"><span data-stu-id="92f8c-124">Thumbprint Use</span></span>

<span data-ttu-id="92f8c-125">\---------- ---</span><span class="sxs-lookup"><span data-stu-id="92f8c-125"></span></span>

<span data-ttu-id="92f8c-126">A9D51A2911C74FABFF7F2A8A994B20857D399107 predefinito</span><span class="sxs-lookup"><span data-stu-id="92f8c-126">A9D51A2911C74FABFF7F2A8A994B20857D399107 Default</span></span>

</div>

<div>

## <a name="reviewing-the-output"></a><span data-ttu-id="92f8c-127">Revisione dell'output</span><span class="sxs-lookup"><span data-stu-id="92f8c-127">Reviewing the output</span></span>

<span data-ttu-id="92f8c-128">Il cmdlet Get-CsCertificate restituisce informazioni simili a quelle seguenti per ogni certificato di Lync Server:</span><span class="sxs-lookup"><span data-stu-id="92f8c-128">The Get-CsCertificate cmdlet returns information similar to the following for each of your Lync Server certificates:</span></span>

<span data-ttu-id="92f8c-129">Emittente: CN = FabrikamCA</span><span class="sxs-lookup"><span data-stu-id="92f8c-129">Issuer : CN=FabrikamCA</span></span>

<span data-ttu-id="92f8c-130">NotAfter: 12/28/2015 3:35:41 PM</span><span class="sxs-lookup"><span data-stu-id="92f8c-130">NotAfter : 12/28/2015 3:35:41 PM</span></span>

<span data-ttu-id="92f8c-131">NotBefore: 1/2/2014 12:49:37 PM</span><span class="sxs-lookup"><span data-stu-id="92f8c-131">NotBefore : 1/2/2014 12:49:37 PM</span></span>

<span data-ttu-id="92f8c-132">NumeroSerie: 611BB01200000000000C</span><span class="sxs-lookup"><span data-stu-id="92f8c-132">SerialNumber : 611BB01200000000000C</span></span>

<span data-ttu-id="92f8c-133">Oggetto: CN = LYNC-SE.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="92f8c-133">Subject : CN=LYNC-SE.fabrikam.com</span></span>

<span data-ttu-id="92f8c-134">AlternativeNames: {sip.fabrikam.com, LYNC-SE.fabrikam.com,</span><span class="sxs-lookup"><span data-stu-id="92f8c-134">AlternativeNames : {sip.fabrikam.com, LYNC-SE.fabrikam.com,</span></span>

<span data-ttu-id="92f8c-135">meet.fabrikam.com, admin.fabrikam.com...}</span><span class="sxs-lookup"><span data-stu-id="92f8c-135">meet.fabrikam.com, admin.fabrikam.com...}</span></span>

<span data-ttu-id="92f8c-136">Identificazione personale: A9D51A2911C74FABFF7F2A8A994B20857D399107</span><span class="sxs-lookup"><span data-stu-id="92f8c-136">Thumbprint : A9D51A2911C74FABFF7F2A8A994B20857D399107</span></span>

<span data-ttu-id="92f8c-137">USA: impostazione predefinita</span><span class="sxs-lookup"><span data-stu-id="92f8c-137">Use : Default</span></span>

<span data-ttu-id="92f8c-138">Di norma, i principali problemi che coinvolgono i certificati di Lync Server coinvolgono date e ore, ad esempio quando i certificati hanno effetto (NotBefore) o quando scadono (NotAfter).</span><span class="sxs-lookup"><span data-stu-id="92f8c-138">As a rule, the top issues involving Lync Server certificates involve dates and times, such as when certificates take effect (NotBefore) or when they expire (NotAfter).</span></span> <span data-ttu-id="92f8c-139">Poiché queste date e ore sono così importanti, è consigliabile limitare i dati restituiti alle informazioni, ad esempio l'uso del certificato, il numero di serie del certificato e la data di scadenza del certificato. è quindi possibile rivedere rapidamente tutti i certificati e quando scadono.</span><span class="sxs-lookup"><span data-stu-id="92f8c-139">Because these dates and times are so important, you might want to limit the returned data to information such as the certificate use, the certificate serial number, and the certificate expiration date; then you can quickly review all the certificates and when they will expire.</span></span> <span data-ttu-id="92f8c-140">Per restituire solo queste informazioni, usare il comando insieme alle opzioni come illustrato:</span><span class="sxs-lookup"><span data-stu-id="92f8c-140">To return just that information, use the command together with the options as shown:</span></span>

`Get-CsCertificate | Select-Object Use, SerialNumber, NotAfter | Sort-Object NotAfter`

<span data-ttu-id="92f8c-141">Questo comando restituisce i dati simili a quelli seguenti, con i certificati ordinati in ordine alla data di scadenza:</span><span class="sxs-lookup"><span data-stu-id="92f8c-141">That command returns data similar to the following, with the certificates sorted in order of their expiration date:</span></span>

<span data-ttu-id="92f8c-142">Usare NumeroSerie NotAfter</span><span class="sxs-lookup"><span data-stu-id="92f8c-142">Use SerialNumber NotAfter</span></span>

<span data-ttu-id="92f8c-143">\--- ------------ --------</span><span class="sxs-lookup"><span data-stu-id="92f8c-143"></span></span>

<span data-ttu-id="92f8c-144">Impostazione predefinita 611BB01200000000000C 12/28/2015 3:35:41 PM</span><span class="sxs-lookup"><span data-stu-id="92f8c-144">Default 611BB01200000000000C 12/28/2015 3:35:41 PM</span></span>

<span data-ttu-id="92f8c-145">WebServicesInteral 32980AA20BBB20000191 02/15/2016 2:16:12 PM</span><span class="sxs-lookup"><span data-stu-id="92f8c-145">WebServicesInteral 32980AA20BBB20000191 02/15/2016 2:16:12 PM</span></span>

<span data-ttu-id="92f8c-146">WebServicesExternal 0451B012003872651A0C 02/20/2016 7:11:58</span><span class="sxs-lookup"><span data-stu-id="92f8c-146">WebServicesExternal 0451B012003872651A0C 02/20/2016 7:11:58 AM</span></span>

<span data-ttu-id="92f8c-147">Se si hanno problemi di certificato, è consigliabile rivedere il AlternativeNames configurato per un certificato.</span><span class="sxs-lookup"><span data-stu-id="92f8c-147">If you have certificate problems, you might want to review the AlternativeNames configured for a certificate.</span></span> <span data-ttu-id="92f8c-148">A prima vista, questo sembra essere un problema.</span><span class="sxs-lookup"><span data-stu-id="92f8c-148">At first glance, that seems to be a problem.</span></span> <span data-ttu-id="92f8c-149">Per impostazione predefinita, a seconda delle dimensioni della finestra della console, Get-CsCertificate potrebbe non essere in grado di visualizzare tutti i nomi:</span><span class="sxs-lookup"><span data-stu-id="92f8c-149">By default, and depending on the size of your console window, Get-CsCertificate might not be able to display all the names:</span></span>

<span data-ttu-id="92f8c-150">AlternativeNames: {sip.fabrikam.com, LYNC.fabrikam.com,</span><span class="sxs-lookup"><span data-stu-id="92f8c-150">AlternativeNames : {sip.fabrikam.com, LYNC.fabrikam.com,</span></span>

<span data-ttu-id="92f8c-151">meet.fabrikam.com, amministratore. Fabrika...}</span><span class="sxs-lookup"><span data-stu-id="92f8c-151">meet.fabrikam.com, admin.fabrika...}</span></span>

<span data-ttu-id="92f8c-152">Per visualizzare tutti i nomi alternativi assegnati a un certificato, usare un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="92f8c-152">To see all the alternative names assigned to a certificate use a command similar to this one:</span></span>

`Get-CsCertificate | Where-Object {$_.SerialNumber -eq "611BB01200000000000C"} | Select-Object -ExpandProperty AlternativeNames`

<span data-ttu-id="92f8c-153">Che dovrebbe mostrare tutti i nomi alternativi nel certificato:</span><span class="sxs-lookup"><span data-stu-id="92f8c-153">That should show you all of the alternative names on the certificate:</span></span>

<span data-ttu-id="92f8c-154">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="92f8c-154">sip.fabrikam.com</span></span>

<span data-ttu-id="92f8c-155">LYNC.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="92f8c-155">LYNC.fabrikam.com</span></span>

<span data-ttu-id="92f8c-156">meet.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="92f8c-156">meet.fabrikam.com</span></span>

<span data-ttu-id="92f8c-157">admin.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="92f8c-157">admin.fabrikam.com</span></span>

<span data-ttu-id="92f8c-158">LYNC-SE.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="92f8c-158">LYNC-SE.fabrikam.com</span></span>

<span data-ttu-id="92f8c-159">Dialin.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="92f8c-159">Dialin.fabrikam.com</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="92f8c-160">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="92f8c-160">See Also</span></span>


[<span data-ttu-id="92f8c-161">Get-CsCertificate</span><span class="sxs-lookup"><span data-stu-id="92f8c-161">Get-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

