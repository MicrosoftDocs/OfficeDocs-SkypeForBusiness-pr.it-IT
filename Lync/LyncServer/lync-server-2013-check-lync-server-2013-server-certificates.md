---
title: 'Lync Server 2013: verificare i certificati del server Lync Server 2013'
description: 'Lync Server 2013: verificare i certificati del server Lync Server 2013.'
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
ms.openlocfilehash: 641651cb425b4fe8bd820bcebfa277084233bb1d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543592"
---
# <a name="check-lync-server-2013-server-certificates"></a><span data-ttu-id="8053f-103">Controllare i certificati del server Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8053f-103">Check Lync Server 2013 server certificates</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8053f-104">_**Ultimo argomento modificato:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="8053f-104">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8053f-105">Pianificazione della verifica</span><span class="sxs-lookup"><span data-stu-id="8053f-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="8053f-106">Mensile</span><span class="sxs-lookup"><span data-stu-id="8053f-106">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8053f-107">Strumento di testing</span><span class="sxs-lookup"><span data-stu-id="8053f-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="8053f-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8053f-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8053f-109">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="8053f-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="8053f-110">Quando si esegue localmente utilizzando Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="8053f-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="8053f-111">Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet Get-CsCertificate.</span><span class="sxs-lookup"><span data-stu-id="8053f-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Get-CsCertificate cmdlet.</span></span> <span data-ttu-id="8053f-112">Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="8053f-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Get-CsCertificate&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="8053f-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8053f-113">Description</span></span>

<span data-ttu-id="8053f-114">Il cmdlet Get-CsCertificate consente di recuperare le informazioni su ognuno dei certificati di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8053f-114">The Get-CsCertificate cmdlet enables you to retrieve information about each of your Lync Server certificates.</span></span> <span data-ttu-id="8053f-115">Questo è particolarmente importante perché i certificati hanno una data di scadenza incorporata.</span><span class="sxs-lookup"><span data-stu-id="8053f-115">That’s especially important because certificates have a built-in expiration date.</span></span> <span data-ttu-id="8053f-116">Ad esempio, i certificati rilasciati in privato scadono in genere dopo 12 mesi.</span><span class="sxs-lookup"><span data-stu-id="8053f-116">For example,, privately-issued certificates typically expire after 12 months.</span></span> <span data-ttu-id="8053f-117">Se uno dei certificati di Lync Server scade, si perderà la funzionalità di accompagnamento fino a quando il certificato non verrà rinnovato o sostituito.</span><span class="sxs-lookup"><span data-stu-id="8053f-117">If any of your Lync Server certificates expire then you'll lose the accompanying functionality until that certificate is renewed or replaced.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="8053f-118">Esecuzione del test</span><span class="sxs-lookup"><span data-stu-id="8053f-118">Running the test</span></span>

<span data-ttu-id="8053f-119">Per restituire informazioni su ognuno dei certificati di Lync Server, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="8053f-119">To return information about each of your Lync Server certificates just run the following command:</span></span>

`Get-CsCertificate`

<span data-ttu-id="8053f-120">In alternativa, è possibile filtrare le informazioni sul certificato restituito in base alla data di scadenza.</span><span class="sxs-lookup"><span data-stu-id="8053f-120">Or, you can filter the return certificate information based on expiration date.</span></span> <span data-ttu-id="8053f-121">Ad esempio, questo comando consente di limitare i dati restituiti ai certificati che scadono (non possono essere utilizzati dopo) il 1 ° giugno 2014:</span><span class="sxs-lookup"><span data-stu-id="8053f-121">For example, this command limits the returned data to certificates that expire (cannot be used after) June 1, 2014:</span></span>

`Get-CsCertificate | Where-Object {$_.NotAfter -lt "6/1/2014"}`

<span data-ttu-id="8053f-122">Per ulteriori informazioni, vedere la documentazione della Guida relativa al cmdlet Get-CsCertificate.</span><span class="sxs-lookup"><span data-stu-id="8053f-122">For more information, see the Help documentation for the Get-CsCertificate cmdlet.</span></span>

<span data-ttu-id="8053f-123">Si noti che, anche se il cmdlet Test-CsCertificateConfiguration esiste, non è molto utile per gli amministratori.</span><span class="sxs-lookup"><span data-stu-id="8053f-123">Note that, although the Test-CsCertificateConfiguration cmdlet exists, it is not very useful to administrators.</span></span> <span data-ttu-id="8053f-124">(Invece, il cmdlet viene utilizzato principalmente dalla configurazione guidata certificati). Anche se il cmdlet funziona, le informazioni restituite sono di valore minimo, come illustrato nell'esempio di output seguente:</span><span class="sxs-lookup"><span data-stu-id="8053f-124">(Instead, that cmdlet is primarily used by the Certificate wizard.) Although the cmdlet works, the information that it returns is of minimal value as shown in the following output example:</span></span>

<span data-ttu-id="8053f-125">Utilizzo di identificazione personale</span><span class="sxs-lookup"><span data-stu-id="8053f-125">Thumbprint Use</span></span>

<span data-ttu-id="8053f-126">\---------- ---</span><span class="sxs-lookup"><span data-stu-id="8053f-126">\---------- ---</span></span>

<span data-ttu-id="8053f-127">A9D51A2911C74FABFF7F2A8A994B20857D399107 predefinito</span><span class="sxs-lookup"><span data-stu-id="8053f-127">A9D51A2911C74FABFF7F2A8A994B20857D399107 Default</span></span>

</div>

<div>

## <a name="reviewing-the-output"></a><span data-ttu-id="8053f-128">Revisione dell'output</span><span class="sxs-lookup"><span data-stu-id="8053f-128">Reviewing the output</span></span>

<span data-ttu-id="8053f-129">Il cmdlet Get-CsCertificate restituisce informazioni simili alle seguenti per ognuno dei certificati di Lync Server:</span><span class="sxs-lookup"><span data-stu-id="8053f-129">The Get-CsCertificate cmdlet returns information similar to the following for each of your Lync Server certificates:</span></span>

<span data-ttu-id="8053f-130">Autorità emittente: CN = FabrikamCA</span><span class="sxs-lookup"><span data-stu-id="8053f-130">Issuer : CN=FabrikamCA</span></span>

<span data-ttu-id="8053f-131">NotAfter: 12/28/2015 3:35:41 PM</span><span class="sxs-lookup"><span data-stu-id="8053f-131">NotAfter : 12/28/2015 3:35:41 PM</span></span>

<span data-ttu-id="8053f-132">NotBefore: 1/2/2014 12:49:37 PM</span><span class="sxs-lookup"><span data-stu-id="8053f-132">NotBefore : 1/2/2014 12:49:37 PM</span></span>

<span data-ttu-id="8053f-133">SerialNumber: 611BB01200000000000C</span><span class="sxs-lookup"><span data-stu-id="8053f-133">SerialNumber : 611BB01200000000000C</span></span>

<span data-ttu-id="8053f-134">Oggetto: CN = LYNC-SE.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="8053f-134">Subject : CN=LYNC-SE.fabrikam.com</span></span>

<span data-ttu-id="8053f-135">AlternativeNames: {sip.fabrikam.com, LYNC-SE.fabrikam.com,</span><span class="sxs-lookup"><span data-stu-id="8053f-135">AlternativeNames : {sip.fabrikam.com, LYNC-SE.fabrikam.com,</span></span>

<span data-ttu-id="8053f-136">meet.fabrikam.com, admin.fabrikam.com...}</span><span class="sxs-lookup"><span data-stu-id="8053f-136">meet.fabrikam.com, admin.fabrikam.com...}</span></span>

<span data-ttu-id="8053f-137">Identificazione personale: A9D51A2911C74FABFF7F2A8A994B20857D399107</span><span class="sxs-lookup"><span data-stu-id="8053f-137">Thumbprint : A9D51A2911C74FABFF7F2A8A994B20857D399107</span></span>

<span data-ttu-id="8053f-138">Utilizzo: impostazione predefinita</span><span class="sxs-lookup"><span data-stu-id="8053f-138">Use : Default</span></span>

<span data-ttu-id="8053f-139">Come regola generale, i principali problemi relativi ai certificati di Lync Server coinvolgono date e ore, ad esempio quando i certificati hanno effetto (NotBefore) o quando scadono (NotAfter).</span><span class="sxs-lookup"><span data-stu-id="8053f-139">As a rule, the top issues involving Lync Server certificates involve dates and times, such as when certificates take effect (NotBefore) or when they expire (NotAfter).</span></span> <span data-ttu-id="8053f-140">Poiché queste date e ore sono importanti, è possibile limitare i dati restituiti a informazioni quali l'utilizzo del certificato, il numero di serie del certificato e la data di scadenza del certificato. sarà quindi possibile esaminare rapidamente tutti i certificati e quando scadranno.</span><span class="sxs-lookup"><span data-stu-id="8053f-140">Because these dates and times are so important, you might want to limit the returned data to information such as the certificate use, the certificate serial number, and the certificate expiration date; then you can quickly review all the certificates and when they will expire.</span></span> <span data-ttu-id="8053f-141">Per restituire solo tali informazioni, utilizzare il comando insieme alle opzioni come illustrato di:</span><span class="sxs-lookup"><span data-stu-id="8053f-141">To return just that information, use the command together with the options as shown:</span></span>

`Get-CsCertificate | Select-Object Use, SerialNumber, NotAfter | Sort-Object NotAfter`

<span data-ttu-id="8053f-142">Questo comando restituisce i dati simili al seguente, con i certificati ordinati in base alla data di scadenza:</span><span class="sxs-lookup"><span data-stu-id="8053f-142">That command returns data similar to the following, with the certificates sorted in order of their expiration date:</span></span>

<span data-ttu-id="8053f-143">Utilizzo di SerialNumber NotAfter</span><span class="sxs-lookup"><span data-stu-id="8053f-143">Use SerialNumber NotAfter</span></span>

<span data-ttu-id="8053f-144">\--- ------------ --------</span><span class="sxs-lookup"><span data-stu-id="8053f-144">\--- ------------ --------</span></span>

<span data-ttu-id="8053f-145">Default 611BB01200000000000C 12/28/2015 3:35:41 PM</span><span class="sxs-lookup"><span data-stu-id="8053f-145">Default 611BB01200000000000C 12/28/2015 3:35:41 PM</span></span>

<span data-ttu-id="8053f-146">WebServicesInteral 32980AA20BBB20000191 02/15/2016 2:16:12 PM</span><span class="sxs-lookup"><span data-stu-id="8053f-146">WebServicesInteral 32980AA20BBB20000191 02/15/2016 2:16:12 PM</span></span>

<span data-ttu-id="8053f-147">WebServicesExternal 0451B012003872651A0C 02/20/2016 7:11:58 AM</span><span class="sxs-lookup"><span data-stu-id="8053f-147">WebServicesExternal 0451B012003872651A0C 02/20/2016 7:11:58 AM</span></span>

<span data-ttu-id="8053f-148">Se si verificano problemi relativi ai certificati, è possibile esaminare la AlternativeNames configurata per un certificato.</span><span class="sxs-lookup"><span data-stu-id="8053f-148">If you have certificate problems, you might want to review the AlternativeNames configured for a certificate.</span></span> <span data-ttu-id="8053f-149">A prima vista, che sembra essere un problema.</span><span class="sxs-lookup"><span data-stu-id="8053f-149">At first glance, that seems to be a problem.</span></span> <span data-ttu-id="8053f-150">Per impostazione predefinita, e a seconda delle dimensioni della finestra della console, Get-CsCertificate potrebbe non essere in grado di visualizzare tutti i nomi:</span><span class="sxs-lookup"><span data-stu-id="8053f-150">By default, and depending on the size of your console window, Get-CsCertificate might not be able to display all the names:</span></span>

<span data-ttu-id="8053f-151">AlternativeNames: {sip.fabrikam.com, LYNC.fabrikam.com,</span><span class="sxs-lookup"><span data-stu-id="8053f-151">AlternativeNames : {sip.fabrikam.com, LYNC.fabrikam.com,</span></span>

<span data-ttu-id="8053f-152">meet.fabrikam.com, admin. Fabrika...}</span><span class="sxs-lookup"><span data-stu-id="8053f-152">meet.fabrikam.com, admin.fabrika...}</span></span>

<span data-ttu-id="8053f-153">Per visualizzare tutti i nomi alternativi assegnati a un certificato, utilizzare un comando simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="8053f-153">To see all the alternative names assigned to a certificate use a command similar to this one:</span></span>

`Get-CsCertificate | Where-Object {$_.SerialNumber -eq "611BB01200000000000C"} | Select-Object -ExpandProperty AlternativeNames`

<span data-ttu-id="8053f-154">Che dovrebbe mostrare tutti i nomi alternativi del certificato:</span><span class="sxs-lookup"><span data-stu-id="8053f-154">That should show you all of the alternative names on the certificate:</span></span>

<span data-ttu-id="8053f-155">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="8053f-155">sip.fabrikam.com</span></span>

<span data-ttu-id="8053f-156">LYNC.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="8053f-156">LYNC.fabrikam.com</span></span>

<span data-ttu-id="8053f-157">meet.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="8053f-157">meet.fabrikam.com</span></span>

<span data-ttu-id="8053f-158">admin.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="8053f-158">admin.fabrikam.com</span></span>

<span data-ttu-id="8053f-159">LYNC-SE.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="8053f-159">LYNC-SE.fabrikam.com</span></span>

<span data-ttu-id="8053f-160">Dialin.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="8053f-160">Dialin.fabrikam.com</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8053f-161">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8053f-161">See Also</span></span>


[<span data-ttu-id="8053f-162">Get-CsCertificate</span><span class="sxs-lookup"><span data-stu-id="8053f-162">Get-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

