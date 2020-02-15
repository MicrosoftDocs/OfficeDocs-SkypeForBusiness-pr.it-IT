---
title: 'Lync Server 2013: verificare i certificati del server Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Check server certificates
ms:assetid: 7b0474e8-0efe-47f0-84eb-a1ba575dabfd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725210(v=OCS.15)
ms:contentKeyID: 63969620
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ebdbfdc4ed0f88d78fc78037a3522c73bd220270
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043508"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="check-lync-server-2013-server-certificates"></a><span data-ttu-id="c393b-102">Controllare i certificati del server Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c393b-102">Check Lync Server 2013 server certificates</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c393b-103">_**Ultimo argomento modificato:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="c393b-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c393b-104">Pianificazione della verifica</span><span class="sxs-lookup"><span data-stu-id="c393b-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="c393b-105">Mensile</span><span class="sxs-lookup"><span data-stu-id="c393b-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c393b-106">Strumento di testing</span><span class="sxs-lookup"><span data-stu-id="c393b-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="c393b-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c393b-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c393b-108">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="c393b-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="c393b-109">Quando si esegue localmente utilizzando Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="c393b-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="c393b-110">Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet Get-CsCertificate.</span><span class="sxs-lookup"><span data-stu-id="c393b-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Get-CsCertificate cmdlet.</span></span> <span data-ttu-id="c393b-111">Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="c393b-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Get-CsCertificate&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="c393b-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c393b-112">Description</span></span>

<span data-ttu-id="c393b-113">Il cmdlet Get-CsCertificate consente di recuperare le informazioni su ognuno dei certificati di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c393b-113">The Get-CsCertificate cmdlet enables you to retrieve information about each of your Lync Server certificates.</span></span> <span data-ttu-id="c393b-114">Questo è particolarmente importante perché i certificati hanno una data di scadenza incorporata.</span><span class="sxs-lookup"><span data-stu-id="c393b-114">That’s especially important because certificates have a built-in expiration date.</span></span> <span data-ttu-id="c393b-115">Ad esempio, i certificati rilasciati in privato scadono in genere dopo 12 mesi.</span><span class="sxs-lookup"><span data-stu-id="c393b-115">For example,, privately-issued certificates typically expire after 12 months.</span></span> <span data-ttu-id="c393b-116">Se uno dei certificati di Lync Server scade, si perderà la funzionalità di accompagnamento fino a quando il certificato non verrà rinnovato o sostituito.</span><span class="sxs-lookup"><span data-stu-id="c393b-116">If any of your Lync Server certificates expire then you'll lose the accompanying functionality until that certificate is renewed or replaced.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="c393b-117">Esecuzione del test</span><span class="sxs-lookup"><span data-stu-id="c393b-117">Running the test</span></span>

<span data-ttu-id="c393b-118">Per restituire informazioni su ognuno dei certificati di Lync Server, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="c393b-118">To return information about each of your Lync Server certificates just run the following command:</span></span>

`Get-CsCertificate`

<span data-ttu-id="c393b-119">In alternativa, è possibile filtrare le informazioni sul certificato restituito in base alla data di scadenza.</span><span class="sxs-lookup"><span data-stu-id="c393b-119">Or, you can filter the return certificate information based on expiration date.</span></span> <span data-ttu-id="c393b-120">Ad esempio, questo comando consente di limitare i dati restituiti ai certificati che scadono (non possono essere utilizzati dopo) il 1 ° giugno 2014:</span><span class="sxs-lookup"><span data-stu-id="c393b-120">For example, this command limits the returned data to certificates that expire (cannot be used after) June 1, 2014:</span></span>

`Get-CsCertificate | Where-Object {$_.NotAfter -lt "6/1/2014"}`

<span data-ttu-id="c393b-121">Per ulteriori informazioni, vedere la documentazione della Guida relativa al cmdlet Get-CsCertificate.</span><span class="sxs-lookup"><span data-stu-id="c393b-121">For more information, see the Help documentation for the Get-CsCertificate cmdlet.</span></span>

<span data-ttu-id="c393b-122">Si noti che, anche se il cmdlet Test-CsCertificateConfiguration esiste, non è molto utile per gli amministratori.</span><span class="sxs-lookup"><span data-stu-id="c393b-122">Note that, although the Test-CsCertificateConfiguration cmdlet exists, it is not very useful to administrators.</span></span> <span data-ttu-id="c393b-123">(Invece, il cmdlet viene utilizzato principalmente dalla configurazione guidata certificati). Anche se il cmdlet funziona, le informazioni restituite sono di valore minimo, come illustrato nell'esempio di output seguente:</span><span class="sxs-lookup"><span data-stu-id="c393b-123">(Instead, that cmdlet is primarily used by the Certificate wizard.) Although the cmdlet works, the information that it returns is of minimal value as shown in the following output example:</span></span>

<span data-ttu-id="c393b-124">Utilizzo di identificazione personale</span><span class="sxs-lookup"><span data-stu-id="c393b-124">Thumbprint Use</span></span>

<span data-ttu-id="c393b-125">\---------- ---</span><span class="sxs-lookup"><span data-stu-id="c393b-125">\---------- ---</span></span>

<span data-ttu-id="c393b-126">A9D51A2911C74FABFF7F2A8A994B20857D399107 predefinito</span><span class="sxs-lookup"><span data-stu-id="c393b-126">A9D51A2911C74FABFF7F2A8A994B20857D399107 Default</span></span>

</div>

<div>

## <a name="reviewing-the-output"></a><span data-ttu-id="c393b-127">Revisione dell'output</span><span class="sxs-lookup"><span data-stu-id="c393b-127">Reviewing the output</span></span>

<span data-ttu-id="c393b-128">Il cmdlet Get-CsCertificate restituisce informazioni simili alle seguenti per ognuno dei certificati di Lync Server:</span><span class="sxs-lookup"><span data-stu-id="c393b-128">The Get-CsCertificate cmdlet returns information similar to the following for each of your Lync Server certificates:</span></span>

<span data-ttu-id="c393b-129">Autorità emittente: CN = FabrikamCA</span><span class="sxs-lookup"><span data-stu-id="c393b-129">Issuer : CN=FabrikamCA</span></span>

<span data-ttu-id="c393b-130">NotAfter: 12/28/2015 3:35:41 PM</span><span class="sxs-lookup"><span data-stu-id="c393b-130">NotAfter : 12/28/2015 3:35:41 PM</span></span>

<span data-ttu-id="c393b-131">NotBefore: 1/2/2014 12:49:37 PM</span><span class="sxs-lookup"><span data-stu-id="c393b-131">NotBefore : 1/2/2014 12:49:37 PM</span></span>

<span data-ttu-id="c393b-132">SerialNumber: 611BB01200000000000C</span><span class="sxs-lookup"><span data-stu-id="c393b-132">SerialNumber : 611BB01200000000000C</span></span>

<span data-ttu-id="c393b-133">Oggetto: CN = LYNC-SE.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="c393b-133">Subject : CN=LYNC-SE.fabrikam.com</span></span>

<span data-ttu-id="c393b-134">AlternativeNames: {sip.fabrikam.com, LYNC-SE.fabrikam.com,</span><span class="sxs-lookup"><span data-stu-id="c393b-134">AlternativeNames : {sip.fabrikam.com, LYNC-SE.fabrikam.com,</span></span>

<span data-ttu-id="c393b-135">meet.fabrikam.com, admin.fabrikam.com...}</span><span class="sxs-lookup"><span data-stu-id="c393b-135">meet.fabrikam.com, admin.fabrikam.com...}</span></span>

<span data-ttu-id="c393b-136">Identificazione personale: A9D51A2911C74FABFF7F2A8A994B20857D399107</span><span class="sxs-lookup"><span data-stu-id="c393b-136">Thumbprint : A9D51A2911C74FABFF7F2A8A994B20857D399107</span></span>

<span data-ttu-id="c393b-137">Utilizzo: impostazione predefinita</span><span class="sxs-lookup"><span data-stu-id="c393b-137">Use : Default</span></span>

<span data-ttu-id="c393b-138">Come regola generale, i principali problemi relativi ai certificati di Lync Server coinvolgono date e ore, ad esempio quando i certificati hanno effetto (NotBefore) o quando scadono (NotAfter).</span><span class="sxs-lookup"><span data-stu-id="c393b-138">As a rule, the top issues involving Lync Server certificates involve dates and times, such as when certificates take effect (NotBefore) or when they expire (NotAfter).</span></span> <span data-ttu-id="c393b-139">Poiché queste date e ore sono importanti, è possibile limitare i dati restituiti a informazioni quali l'utilizzo del certificato, il numero di serie del certificato e la data di scadenza del certificato. sarà quindi possibile esaminare rapidamente tutti i certificati e quando scadranno.</span><span class="sxs-lookup"><span data-stu-id="c393b-139">Because these dates and times are so important, you might want to limit the returned data to information such as the certificate use, the certificate serial number, and the certificate expiration date; then you can quickly review all the certificates and when they will expire.</span></span> <span data-ttu-id="c393b-140">Per restituire solo tali informazioni, utilizzare il comando insieme alle opzioni come illustrato di:</span><span class="sxs-lookup"><span data-stu-id="c393b-140">To return just that information, use the command together with the options as shown:</span></span>

`Get-CsCertificate | Select-Object Use, SerialNumber, NotAfter | Sort-Object NotAfter`

<span data-ttu-id="c393b-141">Questo comando restituisce i dati simili al seguente, con i certificati ordinati in base alla data di scadenza:</span><span class="sxs-lookup"><span data-stu-id="c393b-141">That command returns data similar to the following, with the certificates sorted in order of their expiration date:</span></span>

<span data-ttu-id="c393b-142">Utilizzo di SerialNumber NotAfter</span><span class="sxs-lookup"><span data-stu-id="c393b-142">Use SerialNumber NotAfter</span></span>

<span data-ttu-id="c393b-143">\--- ------------ --------</span><span class="sxs-lookup"><span data-stu-id="c393b-143">\--- ------------ --------</span></span>

<span data-ttu-id="c393b-144">Default 611BB01200000000000C 12/28/2015 3:35:41 PM</span><span class="sxs-lookup"><span data-stu-id="c393b-144">Default 611BB01200000000000C 12/28/2015 3:35:41 PM</span></span>

<span data-ttu-id="c393b-145">WebServicesInteral 32980AA20BBB20000191 02/15/2016 2:16:12 PM</span><span class="sxs-lookup"><span data-stu-id="c393b-145">WebServicesInteral 32980AA20BBB20000191 02/15/2016 2:16:12 PM</span></span>

<span data-ttu-id="c393b-146">WebServicesExternal 0451B012003872651A0C 02/20/2016 7:11:58 AM</span><span class="sxs-lookup"><span data-stu-id="c393b-146">WebServicesExternal 0451B012003872651A0C 02/20/2016 7:11:58 AM</span></span>

<span data-ttu-id="c393b-147">Se si verificano problemi relativi ai certificati, è possibile esaminare la AlternativeNames configurata per un certificato.</span><span class="sxs-lookup"><span data-stu-id="c393b-147">If you have certificate problems, you might want to review the AlternativeNames configured for a certificate.</span></span> <span data-ttu-id="c393b-148">A prima vista, che sembra essere un problema.</span><span class="sxs-lookup"><span data-stu-id="c393b-148">At first glance, that seems to be a problem.</span></span> <span data-ttu-id="c393b-149">Per impostazione predefinita, e a seconda delle dimensioni della finestra della console, Get-CsCertificate potrebbe non essere in grado di visualizzare tutti i nomi:</span><span class="sxs-lookup"><span data-stu-id="c393b-149">By default, and depending on the size of your console window, Get-CsCertificate might not be able to display all the names:</span></span>

<span data-ttu-id="c393b-150">AlternativeNames: {sip.fabrikam.com, LYNC.fabrikam.com,</span><span class="sxs-lookup"><span data-stu-id="c393b-150">AlternativeNames : {sip.fabrikam.com, LYNC.fabrikam.com,</span></span>

<span data-ttu-id="c393b-151">meet.fabrikam.com, admin. Fabrika...}</span><span class="sxs-lookup"><span data-stu-id="c393b-151">meet.fabrikam.com, admin.fabrika...}</span></span>

<span data-ttu-id="c393b-152">Per visualizzare tutti i nomi alternativi assegnati a un certificato, utilizzare un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="c393b-152">To see all the alternative names assigned to a certificate use a command similar to this one:</span></span>

`Get-CsCertificate | Where-Object {$_.SerialNumber -eq "611BB01200000000000C"} | Select-Object -ExpandProperty AlternativeNames`

<span data-ttu-id="c393b-153">Che dovrebbe mostrare tutti i nomi alternativi del certificato:</span><span class="sxs-lookup"><span data-stu-id="c393b-153">That should show you all of the alternative names on the certificate:</span></span>

<span data-ttu-id="c393b-154">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="c393b-154">sip.fabrikam.com</span></span>

<span data-ttu-id="c393b-155">LYNC.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="c393b-155">LYNC.fabrikam.com</span></span>

<span data-ttu-id="c393b-156">meet.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="c393b-156">meet.fabrikam.com</span></span>

<span data-ttu-id="c393b-157">admin.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="c393b-157">admin.fabrikam.com</span></span>

<span data-ttu-id="c393b-158">LYNC-SE.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="c393b-158">LYNC-SE.fabrikam.com</span></span>

<span data-ttu-id="c393b-159">Dialin.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="c393b-159">Dialin.fabrikam.com</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c393b-160">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c393b-160">See Also</span></span>


[<span data-ttu-id="c393b-161">Get-CsCertificate</span><span class="sxs-lookup"><span data-stu-id="c393b-161">Get-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

