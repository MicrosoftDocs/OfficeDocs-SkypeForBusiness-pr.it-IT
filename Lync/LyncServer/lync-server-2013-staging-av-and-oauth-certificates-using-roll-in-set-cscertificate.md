---
title: Gestione temporanea dei certificati AV e OAuth tramite-roll in Set-CsCertificate
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Staging AV and OAuth certificates using -Roll in Set-CsCertificate
ms:assetid: 22dec3cc-4b6b-4df2-b269-5b35df4731a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ660292(v=OCS.15)
ms:contentKeyID: 49354387
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ee572bbf115d1e83476194b0e5c92859886da42f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208407"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="staging-av-and-oauth-certificates-in-lync-server-2013-using--roll-in-set-cscertificate"></a><span data-ttu-id="72f1f-102">Staging AV and OAuth Certificates in Lync Server 2013 using-roll in Set-CsCertificate</span><span class="sxs-lookup"><span data-stu-id="72f1f-102">Staging AV and OAuth certificates in Lync Server 2013 using -Roll in Set-CsCertificate</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="72f1f-103">_**Ultimo argomento modificato:** 2012-11-13_</span><span class="sxs-lookup"><span data-stu-id="72f1f-103">_**Topic Last Modified:** 2012-11-13_</span></span>

<span data-ttu-id="72f1f-104">Le comunicazioni audio/video (A/V) sono un componente chiave di Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="72f1f-104">Audio/Video (A/V) communications is a key component of Microsoft Lync Server 2013.</span></span> <span data-ttu-id="72f1f-105">Funzionalità quali la condivisione di applicazioni e le conferenze audio e video si basano sui certificati assegnati al servizio A/V Edge, in particolare il servizio di autenticazione A/V.</span><span class="sxs-lookup"><span data-stu-id="72f1f-105">Features such as application sharing and audio and video conferencing rely on the certificates assigned to the A/V Edge service, specifically the A/V Authentication service.</span></span>

<div>


> [!IMPORTANT]
> <OL>
> <LI>
> <P><span data-ttu-id="72f1f-106">Questa nuova funzionalità è progettata per funzionare con il servizio A/V Edge e il certificato <EM>OAuthTokenIssuer</EM> .</span><span class="sxs-lookup"><span data-stu-id="72f1f-106">This new feature is designed to work for the A/V Edge service and the <EM>OAuthTokenIssuer</EM> certificate.</span></span> <span data-ttu-id="72f1f-107">È possibile eseguire il provisioning di altri tipi di certificato insieme al servizio A/V Edge e al tipo di certificato OAuth, ma non beneficiare del comportamento di coesistenza del certificato del servizio A/V Edge.</span><span class="sxs-lookup"><span data-stu-id="72f1f-107">Other certificate types can be provisioned along with the A/V Edge service and OAuth certificate type, but will not benefit from the coexistence behavior that the A/V Edge service certificate will.</span></span></P>
> <LI>
> <P><span data-ttu-id="72f1f-108">I cmdlet di PowerShell di Lync Server Management Shell utilizzati per gestire i certificati di Microsoft Lync Server 2013 si riferiscono al certificato del servizio A/V Edge come tipo di certificato <EM>AudioVideoAuthentication</EM> e il certificato OAuthServer come tipo <EM>OAuthTokenIssuer</EM>.</span><span class="sxs-lookup"><span data-stu-id="72f1f-108">The Lync Server Management Shell PowerShell cmdlets used to manage Microsoft Lync Server 2013 certificates refers to the A/V Edge service certificate as the <EM>AudioVideoAuthentication</EM> certificate type and the OAuthServer certificate as type <EM>OAuthTokenIssuer</EM>.</span></span> <span data-ttu-id="72f1f-109">Per il resto di questo argomento e per identificare in modo univoco i certificati, verranno riferiti dallo stesso tipo di identificatore, <EM>AudioVideoAuthentication</EM> e <EM>OAuthTokenIssuer</EM>.</span><span class="sxs-lookup"><span data-stu-id="72f1f-109">For the rest of this topic and to uniquely identify the certificates, they will be referred to by the same identifier type, <EM>AudioVideoAuthentication</EM> and <EM>OAuthTokenIssuer</EM>.</span></span></P></LI></OL>



</div>

<span data-ttu-id="72f1f-110">Il servizio di autenticazione A/V è responsabile dell'emissione di token utilizzati dai client e da altri utenti A/V.</span><span class="sxs-lookup"><span data-stu-id="72f1f-110">The A/V Authentication service is responsible for issuing tokens that are used by clients and other A/V consumers.</span></span> <span data-ttu-id="72f1f-111">I token vengono generati dagli attributi del certificato e, quando il certificato scade, la perdita di connessione e il requisito di riunirsi con un nuovo token generato dal nuovo certificato risultano.</span><span class="sxs-lookup"><span data-stu-id="72f1f-111">The tokens are generated from attributes on the certificate, and when the certificate expires, loss of connection and requirement to rejoin with a new token generated by the new certificate will result.</span></span> <span data-ttu-id="72f1f-112">Una nuova funzionalità di Lync Server 2013 consente di alleviare questo problema: la possibilità di eseguire un nuovo certificato prima della scadenza e di consentire a entrambi i certificati di continuare a funzionare per un determinato periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="72f1f-112">A new feature in Lync Server 2013 will alleviate this problem – the ability to stage a new certificate in advance of the old one expiring and allowing both certificates to continue to function for a period of time.</span></span> <span data-ttu-id="72f1f-113">Questa funzionalità utilizza la funzionalità aggiornata nel cmdlet Set-CsCertificate di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="72f1f-113">This feature uses updated functionality in the Set-CsCertificate Lync Server Management Shell cmdlet.</span></span> <span data-ttu-id="72f1f-114">Il nuovo parametro-roll, con il parametro existing-EffectiveDate, inserirà il nuovo certificato AudioVideoAuthentication nell'archivio certificati.</span><span class="sxs-lookup"><span data-stu-id="72f1f-114">The new parameter –Roll, with the existing parameter –EffectiveDate, will place the new AudioVideoAuthentication certificate in the certificate store.</span></span> <span data-ttu-id="72f1f-115">Il certificato AudioVideoAuthentication meno recente continuerà a essere convalidato per i token emessi.</span><span class="sxs-lookup"><span data-stu-id="72f1f-115">The older AudioVideoAuthentication certificate will still remain for issued tokens to be validated against.</span></span> <span data-ttu-id="72f1f-116">A partire dalla messa in posizione del nuovo certificato AudioVideoAuthentication, si verificherà la seguente serie di eventi:</span><span class="sxs-lookup"><span data-stu-id="72f1f-116">Beginning with putting the new AudioVideoAuthentication certificate in place, the following series of events will occur:</span></span>

<div>


> [!TIP]
> <span data-ttu-id="72f1f-117">Utilizzando i cmdlet di Lync Server Management Shell per la gestione dei certificati, è possibile richiedere certificati separati e distinti per ogni scopo nel server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="72f1f-117">Using the Lync Server Management Shell cmdlets for managing certificates, you can request separate and distinct certificates for each purpose on the Edge Server.</span></span> <span data-ttu-id="72f1f-118">L'utilizzo della configurazione guidata certificati nella distribuzione guidata di Lync Server consente di creare certificati, ma in genere è il tipo <STRONG>predefinito</STRONG> per il quale tutti i certificati vengono utilizzati per il server perimetrale su un singolo certificato.</span><span class="sxs-lookup"><span data-stu-id="72f1f-118">Using the Certificate Wizard in the Lync Server Deployment Wizard assists you in creating certificates, but is typically of the <STRONG>default</STRONG> type which couples all certificate uses for the Edge Server onto a single certificate.</span></span> <span data-ttu-id="72f1f-119">Se si intende utilizzare la funzionalità di certificati in sequenza, la procedura consigliata consiste nel disassociare il certificato AudioVideoAuthentication dagli scopi degli altri certificati.</span><span class="sxs-lookup"><span data-stu-id="72f1f-119">The recommended practice if you are going to use the rolling certificate feature is to decouple the AudioVideoAuthentication certificate from the other certificate purposes.</span></span> <span data-ttu-id="72f1f-120">È possibile effettuare il provisioning e gestire temporaneamente un certificato di tipo predefinito, ma solo la parte AudioVideoAuthentication del certificato combinato sfrutterà i vantaggi della gestione temporanea.</span><span class="sxs-lookup"><span data-stu-id="72f1f-120">You can provision and stage a certificate of the Default type, but only the AudioVideoAuthentication portion of the combined certificate will benefit from the staging.</span></span> <span data-ttu-id="72f1f-121">Un utente coinvolto (ad esempio) una conversazione di messaggistica istantanea quando il certificato scade avrà bisogno di disconnettersi e accedere nuovamente per utilizzare il nuovo certificato associato al servizio Access Edge.</span><span class="sxs-lookup"><span data-stu-id="72f1f-121">A user involved in (for example) an instant messaging conversation when the certificate expires will need to log out and log back in to make use of the new certificate associated with the Access Edge service.</span></span> <span data-ttu-id="72f1f-122">Si verificherà un comportamento analogo per un utente coinvolto in una conferenza Web tramite il servizio Web Conferencing Edge.</span><span class="sxs-lookup"><span data-stu-id="72f1f-122">Similar behavior will occur for a user involved in a Web conference using the Web Conferencing Edge service.</span></span> <span data-ttu-id="72f1f-123">Il certificato OAuthTokenIssuer è un tipo specifico condiviso in tutti i server.</span><span class="sxs-lookup"><span data-stu-id="72f1f-123">The OAuthTokenIssuer certificate is a specific type that is shared across all servers.</span></span> <span data-ttu-id="72f1f-124">È possibile creare e gestire il certificato in un'unica posizione e il certificato viene archiviato nell'archivio di gestione centrale per tutti gli altri server.</span><span class="sxs-lookup"><span data-stu-id="72f1f-124">You create and manage the certificate in one place and the certificate is stored in the Central Management store for all other servers.</span></span>



</div>

<span data-ttu-id="72f1f-125">Per comprendere appieno le opzioni e i requisiti relativi all'uso del cmdlet Set-CsCertificate e alla gestione temporanea di certificati tramite tale cmdlet prima della scadenza del certificato corrente, sono necessarie altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="72f1f-125">Additional detail is needed to fully understand your options and requirements when using the Set-CsCertificate cmdlet and using it to stage certificates prior to the current certificate expiring.</span></span> <span data-ttu-id="72f1f-126">Il parametro –Roll è importante, ma ha essenzialmente un solo scopo.</span><span class="sxs-lookup"><span data-stu-id="72f1f-126">The –Roll parameter is important, but essentially single purpose.</span></span> <span data-ttu-id="72f1f-127">Se lo si definisce come parametro, si sta dicendo a Set-CsCertificate che verranno fornite informazioni sul certificato che sarà influenzato da – tipo (ad esempio AudioVideoAuthentication e OAuthTokenIssuer), quando il certificato diventerà effetto definito da – EffectiveDate.</span><span class="sxs-lookup"><span data-stu-id="72f1f-127">If you define it as a parameter, you are telling Set-CsCertificate that you will be providing information about the certificate that will be affected defined by –Type (for example AudioVideoAuthentication and OAuthTokenIssuer), when the certificate will become effective defined by –EffectiveDate.</span></span>

<span data-ttu-id="72f1f-128">**-Roll:** Il parametro – Roll è obbligatorio e dispone di dipendenze che devono essere fornite insieme.</span><span class="sxs-lookup"><span data-stu-id="72f1f-128">**-Roll:** The –Roll parameter is required and has dependencies that must be supplied along with it.</span></span> <span data-ttu-id="72f1f-129">Parametri obbligatori per definire completamente quali certificati saranno interessati e come saranno applicati:</span><span class="sxs-lookup"><span data-stu-id="72f1f-129">Required parameters to fully define which certificates will be affected and how they will be applied:</span></span>

<span data-ttu-id="72f1f-130">**-EffectiveDate:** Il parametro – EffectiveDate definisce quando il nuovo certificato diventerà coattivo con il certificato corrente.</span><span class="sxs-lookup"><span data-stu-id="72f1f-130">**-EffectiveDate:** The parameter –EffectiveDate defines when the new certificate will become co-active with the current certificate.</span></span> <span data-ttu-id="72f1f-131">Il parametro –EffectiveDate può essere vicino all'ora di scadenza del certificato corrente oppure corrispondere a un periodo di tempo più lungo.</span><span class="sxs-lookup"><span data-stu-id="72f1f-131">The –EffectiveDate can be close to the expiry time of the current certificate, or it can be a longer period of time.</span></span> <span data-ttu-id="72f1f-132">Un valore minimo consigliato per –EffectiveDate per il certificato AudioVideoAuthentication è di 8 ore, ovvero la durata predefinita del token per i token del servizio A/V Edge emessi utilizzando il certificato AudioVideoAuthentication.</span><span class="sxs-lookup"><span data-stu-id="72f1f-132">A recommended minimum –EffectiveDate for the AudioVideoAuthentication certificate would be 8 hours, which is the default token lifetime for AV Edge service tokens issued using the AudioVideoAuthentication certificate.</span></span>

<span data-ttu-id="72f1f-p109">Quando si gestiscono temporaneamente certificati OAuthTokenIssuer, esistono diversi requisiti per il tempo di anticipo prima che il certificato diventi effettivo. Il tempo di anticipo minimo per il certificato OAuthTokenIssuer è di 24 ore prima dell'ora di scadenza del certificato corrente. Il tempo di anticipo prolungato per la coesistenza è dovuto ad altri ruoli del server dipendenti dal certificato OAuthTokenIssuer (ad esempio Exchange Server) che ha un periodo di memorizzazione più lungo per i materiali di autenticazione e chiave di crittografia creati dal certificato.</span><span class="sxs-lookup"><span data-stu-id="72f1f-p109">When staging OAuthTokenIssuer certificates, there are different requirements for the lead time before the certificate can become effective. The minimum time that the OAuthTokenIssuer certificate should have for its lead time is 24 hours before the expiration time of the current certificate. The extended lead time for the coexistence is because of other server roles that are dependent on the OAuthTokenIssuer certificate (Exchange Server, for example) which has a longer retention time for certificate created authentication and encryption key materials.</span></span>

<span data-ttu-id="72f1f-136">**-Identificazione personale:** L'identificazione personale è un attributo del certificato univoco per il certificato.</span><span class="sxs-lookup"><span data-stu-id="72f1f-136">**-Thumbprint:** The thumbprint is an attribute on the certificate that is unique to that certificate.</span></span> <span data-ttu-id="72f1f-137">Il parametro –Thumbprint è utilizzato per identificare il certificato che sarà interessato dalle azioni del cmdlet Set-CsCertificate.</span><span class="sxs-lookup"><span data-stu-id="72f1f-137">The –Thumbprint parameter is used to identify the certificate that will be affected by the actions of the Set-CsCertificate cmdlet.</span></span>

<span data-ttu-id="72f1f-138">**-Digitare:** Il parametro – Type può accettare un singolo tipo di utilizzo del certificato o un elenco separato da virgole di tipi di utilizzo dei certificati.</span><span class="sxs-lookup"><span data-stu-id="72f1f-138">**-Type:** The –Type parameter can accept a single certificate usage type or a comma separated list of certificate usage types.</span></span> <span data-ttu-id="72f1f-139">I tipi di certificati identificato lo scopo del certificato per il cmdlet e il server.</span><span class="sxs-lookup"><span data-stu-id="72f1f-139">The certificate types are those that identify to the cmdlet and to the server what the purpose of the certificate is.</span></span> <span data-ttu-id="72f1f-140">Ad esempio, digitare AudioVideoAuthentication è per l'utilizzo da parte del servizio A/V Edge e del servizio di autenticazione AV.</span><span class="sxs-lookup"><span data-stu-id="72f1f-140">For example, type AudioVideoAuthentication is for use by the A/V Edge service and the AV Authentication service.</span></span> <span data-ttu-id="72f1f-141">Se si decide di gestire temporaneamente ed effettuare il provisioning di certificati di un tipo diverso contemporaneamente, è necessario considerare il più lungo tempo di anticipo effettivo minimo richiesto per i certificati.</span><span class="sxs-lookup"><span data-stu-id="72f1f-141">If you decide to stage and provision certificates of a different type at the same time, you must consider the longest required minimum effective lead time for the certificates.</span></span> <span data-ttu-id="72f1f-142">Ad esempio, è necessario gestire temporaneamente i certificati di tipo AudioVideoAuthentication e OAuthTokenIssuer.</span><span class="sxs-lookup"><span data-stu-id="72f1f-142">For example, you need to stage certificates of type AudioVideoAuthentication and OAuthTokenIssuer.</span></span> <span data-ttu-id="72f1f-143">Il valore minimo di –EffectiveDate deve essere il maggiore dei due certificati, in questo caso OAuthTokenIssuer, che ha un tempo di anticipo di almeno 24 ore.</span><span class="sxs-lookup"><span data-stu-id="72f1f-143">Your minimum –EffectiveDate must be the greater of the two certificates, in this case the OAuthTokenIssuer, which has a minimum lead time of 24 hours.</span></span> <span data-ttu-id="72f1f-144">Se non si desidera gestire temporaneamente il certificato AudioVideoAuthentication con un tempo di anticipo di 24 ore, gestirlo separatamente con un valore di EffectiveDate più adeguato ai requisiti specifici.</span><span class="sxs-lookup"><span data-stu-id="72f1f-144">If you do not want to stage the AudioVideoAuthentication certificate with a lead time of 24 hours, stage it separately with an EffectiveDate that is more to your requirements.</span></span>

<div>

## <a name="to-update-or-renew-an-av-edge-service-certificate-with-a-roll-and--effectivedate-parameters"></a><span data-ttu-id="72f1f-145">Per aggiornare o rinnovare un certificato del servizio A/V Edge con i parametri-roll e-EffectiveDate</span><span class="sxs-lookup"><span data-stu-id="72f1f-145">To update or renew an A/V Edge service certificate with a –Roll and -EffectiveDate parameters</span></span>

1.  <span data-ttu-id="72f1f-146">Accedere al computer locale come membro del gruppo Administrators.</span><span class="sxs-lookup"><span data-stu-id="72f1f-146">Log on to the local computer as a member of the Administrators group.</span></span>

2.  <span data-ttu-id="72f1f-147">Richiedere un rinnovo o un nuovo certificato AudioVideoAuthentication con una chiave privata esportabile per il certificato esistente nel servizio A/V Edge.</span><span class="sxs-lookup"><span data-stu-id="72f1f-147">Request a renewal or new AudioVideoAuthentication certificate with exportable private key for the existing certificate on the A/V Edge service.</span></span>

3.  <span data-ttu-id="72f1f-148">Importare il nuovo certificato di AudioVideoAuthentication nel server perimetrale e in tutti gli altri server perimetrali del pool (se è stato distribuito un pool).</span><span class="sxs-lookup"><span data-stu-id="72f1f-148">Import the new AudioVideoAuthentication certificate to the Edge Server and all other Edge Server in your pool (if you have a pool deployed).</span></span>

4.  <span data-ttu-id="72f1f-149">Configurare il certificato importato con il cmdlet Set-CsCertificate e utilizzare il parametro –Roll con il parametro –EffectiveDate.</span><span class="sxs-lookup"><span data-stu-id="72f1f-149">Configure the imported certificate with the Set-CsCertificate cmdlet and use the –Roll parameter with the –EffectiveDate parameter.</span></span> <span data-ttu-id="72f1f-150">La data effettiva deve essere definita come ora di scadenza del certificato corrente (14:00:00 o 2:00:00 PM) meno la durata del token (otto ore per impostazione predefinita).</span><span class="sxs-lookup"><span data-stu-id="72f1f-150">The effective date should be defined as the current certificate expire time (14:00:00, or 2:00:00 PM) minus token lifetime (by default eight hours).</span></span> <span data-ttu-id="72f1f-151">In questo modo viene indicato che il certificato deve essere impostato su attivo ed è la stringa \<\>– EFFECTIVEDATE: "7/22/2012 6:00:00 AM".</span><span class="sxs-lookup"><span data-stu-id="72f1f-151">This gives us a time that the certificate must be set to active, and is the –EffectiveDate \<string\>: “7/22/2012 6:00:00 AM”.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="72f1f-152">Per un pool di server perimetrali, è necessario disporre di tutti i certificati di AudioVideoAuthentication distribuiti e provisionati in base alla data e all'ora definite dal parametro – EffectiveDate del primo certificato distribuito per evitare possibili interruzioni di comunicazioni a/V a causa del certificato meno recente che scade prima che tutti i client e i token consumer siano stati rinnovati utilizzando il nuovo certificato.</span><span class="sxs-lookup"><span data-stu-id="72f1f-152">For an Edge pool, you must have all AudioVideoAuthentication certificates deployed and provisioned by the date and time defined by the –EffectiveDate parameter of the first certificate deployed to avoid possible A/V communications disruption due to the older certificate expiring before all client and consumer tokens have been renewed using the new certificate.</span></span>

    
    </div>
    
    <span data-ttu-id="72f1f-153">Comando Set-CsCertificate con i parametri –Roll e –EffectiveTime:</span><span class="sxs-lookup"><span data-stu-id="72f1f-153">The Set-CsCertificate command with the –Roll and –EffectiveTime parameter:</span></span>
    
        Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint <thumb print of new certificate> -Roll -EffectiveDate <date and time for certificate to become active>
    
    <span data-ttu-id="72f1f-154">Esempio di comando Set-CsCertificate:</span><span class="sxs-lookup"><span data-stu-id="72f1f-154">An example Set-CsCertificate command:</span></span>
    
        Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/22/2012 6:00:00 AM"
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="72f1f-p113">È necessario formattare il parametro EffectiveDate secondo le impostazioni di lingua e paese del server. Nell'esempio vengono utilizzate le impostazioni di paese e lingua Inglese (Stati Uniti).</span><span class="sxs-lookup"><span data-stu-id="72f1f-p113">The EffectiveDate must be formatted to match your server’s region and language settings. The example uses the US English Region and Language settings</span></span>

    
    </div>

<span data-ttu-id="72f1f-157">Per capire meglio il processo utilizzato da Set-CsCertificate, -Roll e –EffectiveDate per gestire temporaneamente un nuovo certificato per l'emissione di nuovi token AudioVideoAuthentication pur continuando a utilizzare un certificato esistente per convalidare token AudioVideoAuthentication utilizzati dai consumer, è utile servirsi di una sequenza temporale visiva.</span><span class="sxs-lookup"><span data-stu-id="72f1f-157">To further understand the process that Set-CsCertificate, -Roll, and –EffectiveDate use to stage a new certificate for issuing new AudioVideoAuthentication tokens while still using an existing certificate to validate AudioVideoAuthentication that are in use by consumers, a visual timeline is an effective means of understanding the process.</span></span>

<span data-ttu-id="72f1f-158">Nell'esempio seguente l'amministratore determina che il certificato del servizio A/V Edge deve scadere alle 2:00:00 PM del 07/22/2012.</span><span class="sxs-lookup"><span data-stu-id="72f1f-158">In the following example, the administrator determines that the A/V Edge service certificate is due to expire at 2:00:00 PM on 07/22/2012.</span></span> <span data-ttu-id="72f1f-159">Richiede e riceve un nuovo certificato e lo importa in ogni server perimetrale del pool.</span><span class="sxs-lookup"><span data-stu-id="72f1f-159">He requests and receives a new certificate and imports it to each Edge Server in his pool.</span></span> <span data-ttu-id="72f1f-160">Alle 2.00 del 22/07/2012 inizia a eseguire Get-CsCertificate con –Roll, -Thumbprint equivalente alla stringa di identificatore digitale del nuovo certificato e –EffectiveTime impostato su 22/07/2012 6.00.</span><span class="sxs-lookup"><span data-stu-id="72f1f-160">At 2 AM on 07/22/2012, he begins running Get-CsCertificate with –Roll, -Thumbprint equal to the thumbprint string of the new certificate, and –EffectiveTime set to 07/22/2012 6:00:00 AM.</span></span> <span data-ttu-id="72f1f-161">Esegue questo comando in ogni server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="72f1f-161">He runs this command on each Edge Server.</span></span>

<span data-ttu-id="72f1f-162">![Utilizzo dei parametri roll e EffectiveDate.](images/JJ660292.21d51a76-0d03-4ed7-a37e-a7c14940265f(OCS.15).jpg "Utilizzo dei parametri roll e EffectiveDate.")</span><span class="sxs-lookup"><span data-stu-id="72f1f-162">![Using the Roll and the EffectiveDate parameters.](images/JJ660292.21d51a76-0d03-4ed7-a37e-a7c14940265f(OCS.15).jpg "Using the Roll and the EffectiveDate parameters.")</span></span>

<span data-ttu-id="72f1f-p115">All'ora effettiva (6.00 del 22/7/2012), tutti i nuovi token vengono emessi dal nuovo certificato. Alla convalida, i token verranno prima convalidati rispetto al nuovo certificato e, in caso di esito negativo, verrà effettuato un tentativo con il vecchio certificato. Questo processo che prevede prima l'uso del nuovo certificato e del vecchio certificato come fallback viene ripetuto fino alla scadenza del vecchio certificato. Una volta scaduto il vecchio certificato (22/7/2012 alle 14.00), i token verranno convalidati solo mediante il nuovo certificato. Il vecchio certificato potrà essere rimosso senza problemi utilizzando il cmdlet Remove-CsCertificate con il parametro –Previous.</span><span class="sxs-lookup"><span data-stu-id="72f1f-p115">When the effective time is reached (7/22/2012 6:00:00 AM), all new tokens are issued by the new certificate. When validating tokens, tokens will first be validated against the new certificate. If the validation fails, the old certificate is tried. The process of trying the new and falling back to the old certificate will continue until the expiry time of the old certificate. Once the old certificate has expired (7/22/2012 2:00:00 PM), tokens will only be validated by the new certificate. The old certificate can be safely removed using the Remove-CsCertificate cmdlet with the –Previous parameter.</span></span>

    Remove-CsCertificate -Type AudioVideoAuthentication -Previous

</div>

<div>

## <a name="to-update-or-renew-an-oauthtokenissuer-certificate-with-a-roll-and--effectivedate-parameters"></a><span data-ttu-id="72f1f-169">Per aggiornare o rinnovare un certificato OAuthTokenIssuer con parametri –Roll e -EffectiveDate</span><span class="sxs-lookup"><span data-stu-id="72f1f-169">To update or renew an OAuthTokenIssuer certificate with a –Roll and -EffectiveDate parameters</span></span>

1.  <span data-ttu-id="72f1f-170">Accedere al computer locale come membro del gruppo Administrators.</span><span class="sxs-lookup"><span data-stu-id="72f1f-170">Log on to the local computer as a member of the Administrators group.</span></span>

2.  <span data-ttu-id="72f1f-171">Richiedere un rinnovo o un nuovo certificato OAuthTokenIssuer con una chiave privata esportabile per il certificato esistente nel servizio A/V Edge.</span><span class="sxs-lookup"><span data-stu-id="72f1f-171">Request a renewal or new OAuthTokenIssuer certificate with exportable private key for the existing certificate on the A/V Edge service.</span></span>

3.  <span data-ttu-id="72f1f-172">Importare il nuovo certificato di OAuthTokenIssuer in un front end server nel pool (se è stato distribuito un pool).</span><span class="sxs-lookup"><span data-stu-id="72f1f-172">Import the new OAuthTokenIssuer certificate to a Front End Server in your pool (if you have a pool deployed).</span></span> <span data-ttu-id="72f1f-173">Il certificato OAuthTokenIssuer viene replicato globalmente e deve solo essere aggiornato e rinnovato in ogni server nella distribuzione.</span><span class="sxs-lookup"><span data-stu-id="72f1f-173">The OAuthTokenIssuer certificate is replicated globally and only needs to be updated and renewed at any server in your deployment.</span></span> <span data-ttu-id="72f1f-174">Il front end server viene utilizzato come esempio.</span><span class="sxs-lookup"><span data-stu-id="72f1f-174">The Front End Server is used as an example.</span></span>

4.  <span data-ttu-id="72f1f-p117">Configurare il certificato importato con il cmdlet Set-CsCertificate e utilizzare il parametro –Roll con il parametro –EffectiveDate. La data effettiva deve essere definita come ora di scadenza del certificato corrente (14:00:00 o 2:00:00 PM) meno un minimo di 24 ore.</span><span class="sxs-lookup"><span data-stu-id="72f1f-p117">Configure the imported certificate with the Set-CsCertificate cmdlet and use the –Roll parameter with the –EffectiveDate parameter. The effective date should be defined as the current certificate expire time (14:00:00, or 2:00:00 PM) minus a minimum of 24 hours.</span></span>
    
    <span data-ttu-id="72f1f-177">Comando Set-CsCertificate con i parametri –Roll e –EffectiveTime:</span><span class="sxs-lookup"><span data-stu-id="72f1f-177">The Set-CsCertificate command with the –Roll and –EffectiveTime parameter:</span></span>
    
        Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint <thumb print of new certificate> -Roll -EffectiveDate <date and time for certificate to become active>
    
    <span data-ttu-id="72f1f-178">Esempio di comando Set-CsCertificate:</span><span class="sxs-lookup"><span data-stu-id="72f1f-178">An example Set-CsCertificate command:</span></span>
    
        Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/21/2012 1:00:00 PM"
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="72f1f-p118">È necessario formattare il parametro EffectiveDate secondo le impostazioni di lingua e paese del server. Nell'esempio vengono utilizzate le impostazioni di paese e lingua Inglese (Stati Uniti).</span><span class="sxs-lookup"><span data-stu-id="72f1f-p118">The EffectiveDate must be formatted to match your server’s region and language settings. The example uses the US English Region and Language settings</span></span>

    
    </div>

<span data-ttu-id="72f1f-p119">All'ora effettiva (1.00.00 del 21/07/2012), tutti i nuovi token vengono emessi dal nuovo certificato. Alla convalida, i token verranno prima convalidati rispetto al nuovo certificato e, in caso di esito negativo, verrà effettuato un tentativo con il vecchio certificato. Questo processo che prevede prima l'uso del nuovo certificato e del vecchio certificato come fallback viene ripetuto fino alla scadenza del vecchio certificato. Una volta scaduto il vecchio certificato (22/7/2012 alle 14.00), i token verranno convalidati solo mediante il nuovo certificato. Il vecchio certificato potrà essere rimosso senza problemi utilizzando il cmdlet Remove-CsCertificate con il parametro –Previous.</span><span class="sxs-lookup"><span data-stu-id="72f1f-p119">When the effective time is reached (7/21/2012 1:00:00 AM), all new tokens are issued by the new certificate. When validating tokens, tokens will first be validated against the new certificate. If the validation fails, the old certificate is tried. The process of trying the new and falling back to the old certificate will continue until the expiry time of the old certificate. Once the old certificate has expired (7/22/2012 2:00:00 PM), tokens will only be validated by the new certificate. The old certificate can be safely removed using the Remove-CsCertificate cmdlet with the –Previous parameter.</span></span>

    Remove-CsCertificate -Type OAuthTokenIssuer -Previous

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="72f1f-187">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="72f1f-187">See Also</span></span>


[<span data-ttu-id="72f1f-188">Pianificare i certificati dei server perimetrali in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="72f1f-188">Plan for Edge Server certificates in Lync Server 2013</span></span>](lync-server-2013-plan-for-edge-server-certificates.md)  
[<span data-ttu-id="72f1f-189">Gestione dell'autenticazione da server a server (OAuth) e delle applicazioni partner in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="72f1f-189">Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013</span></span>](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)  


[<span data-ttu-id="72f1f-190">Configurare i certificati perimetrali per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="72f1f-190">Set up Edge certificates for Lync Server 2013</span></span>](lync-server-2013-set-up-edge-certificates.md)  
<span data-ttu-id="72f1f-191">[Set-CsCertificate](https://technet.microsoft.com/library/Gg398518(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="72f1f-191">[Set-CsCertificate](https://technet.microsoft.com/library/Gg398518(v=OCS.15))</span></span>  
<span data-ttu-id="72f1f-192">[Remove-CsCertificate](https://technet.microsoft.com/library/Gg412895(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="72f1f-192">[Remove-CsCertificate](https://technet.microsoft.com/library/Gg412895(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

