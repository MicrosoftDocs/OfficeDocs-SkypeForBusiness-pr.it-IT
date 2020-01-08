---
title: Gestione di certificati AV e OAuth con-roll in Set-CsCertificate
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Staging AV and OAuth certificates using -Roll in Set-CsCertificate
ms:assetid: 22dec3cc-4b6b-4df2-b269-5b35df4731a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ660292(v=OCS.15)
ms:contentKeyID: 49354387
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4acdf759181dee3df872c7803ec595c63fb07016
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977689"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="staging-av-and-oauth-certificates-in-lync-server-2013-using--roll-in-set-cscertificate"></a><span data-ttu-id="3f1f8-102">Gestione di certificati AV e OAuth in Lync Server 2013 con-roll in Set-CsCertificate</span><span class="sxs-lookup"><span data-stu-id="3f1f8-102">Staging AV and OAuth certificates in Lync Server 2013 using -Roll in Set-CsCertificate</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3f1f8-103">_**Argomento Ultima modifica:** 2012-11-13_</span><span class="sxs-lookup"><span data-stu-id="3f1f8-103">_**Topic Last Modified:** 2012-11-13_</span></span>

<span data-ttu-id="3f1f8-104">Le comunicazioni audio/video (A/V) sono un componente chiave di Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-104">Audio/Video (A/V) communications is a key component of Microsoft Lync Server 2013.</span></span> <span data-ttu-id="3f1f8-105">Le caratteristiche come la condivisione delle applicazioni e le conferenze audio e video si basano sui certificati assegnati al servizio a/V Edge, in particolare il servizio di autenticazione A/V.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-105">Features such as application sharing and audio and video conferencing rely on the certificates assigned to the A/V Edge service, specifically the A/V Authentication service.</span></span>

<div>


> [!IMPORTANT]
> <OL>
> <LI>
> <P><span data-ttu-id="3f1f8-106">Questa nuova funzionalità è progettata per l'utilizzo per il servizio A/V Edge e per il certificato <EM>OAuthTokenIssuer</EM> .</span><span class="sxs-lookup"><span data-stu-id="3f1f8-106">This new feature is designed to work for the A/V Edge service and the <EM>OAuthTokenIssuer</EM> certificate.</span></span> <span data-ttu-id="3f1f8-107">È possibile effettuare il provisioning di altri tipi di certificato insieme al servizio A/V Edge e al tipo di certificato OAuth, ma non beneficiano del comportamento di coesistenza che verrà eseguito dal certificato del servizio A/V Edge.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-107">Other certificate types can be provisioned along with the A/V Edge service and OAuth certificate type, but will not benefit from the coexistence behavior that the A/V Edge service certificate will.</span></span></P>
> <LI>
> <P><span data-ttu-id="3f1f8-108">I cmdlet di PowerShell di Lync Server Management Shell usati per gestire i certificati di Microsoft Lync Server 2013 si riferiscono al certificato del servizio A/V Edge come tipo di certificato <EM>AudioVideoAuthentication</EM> e al certificato OAuthServer come tipo <EM>OAuthTokenIssuer</EM>.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-108">The Lync Server Management Shell PowerShell cmdlets used to manage Microsoft Lync Server 2013 certificates refers to the A/V Edge service certificate as the <EM>AudioVideoAuthentication</EM> certificate type and the OAuthServer certificate as type <EM>OAuthTokenIssuer</EM>.</span></span> <span data-ttu-id="3f1f8-109">Per il resto di questo argomento e per identificare in modo univoco i certificati, questi verranno definiti dallo stesso tipo di identificatore, <EM>AudioVideoAuthentication</EM> e <EM>OAuthTokenIssuer</EM>.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-109">For the rest of this topic and to uniquely identify the certificates, they will be referred to by the same identifier type, <EM>AudioVideoAuthentication</EM> and <EM>OAuthTokenIssuer</EM>.</span></span></P></LI></OL>



</div>

<span data-ttu-id="3f1f8-110">Il servizio di autenticazione A/V è responsabile per il rilascio di token usati dai client e da altri utenti A/V.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-110">The A/V Authentication service is responsible for issuing tokens that are used by clients and other A/V consumers.</span></span> <span data-ttu-id="3f1f8-111">I token vengono generati dagli attributi del certificato e quando il certificato scade, la perdita di connessione e il requisito di ricongiungersi con un nuovo token generato dal nuovo certificato si tradurrà.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-111">The tokens are generated from attributes on the certificate, and when the certificate expires, loss of connection and requirement to rejoin with a new token generated by the new certificate will result.</span></span> <span data-ttu-id="3f1f8-112">Una nuova funzionalità di Lync Server 2013 allevierà questo problema: la possibilità di organizzare un nuovo certificato prima della scadenza e consentendo a entrambi i certificati di continuare a funzionare per un periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-112">A new feature in Lync Server 2013 will alleviate this problem – the ability to stage a new certificate in advance of the old one expiring and allowing both certificates to continue to function for a period of time.</span></span> <span data-ttu-id="3f1f8-113">Questa funzionalità Usa la funzionalità aggiornata nel cmdlet Set-CsCertificate di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-113">This feature uses updated functionality in the Set-CsCertificate Lync Server Management Shell cmdlet.</span></span> <span data-ttu-id="3f1f8-114">Il nuovo parametro-roll, con il parametro esistente-EffectiveDate, inserisce il nuovo certificato AudioVideoAuthentication nell'archivio certificati.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-114">The new parameter –Roll, with the existing parameter –EffectiveDate, will place the new AudioVideoAuthentication certificate in the certificate store.</span></span> <span data-ttu-id="3f1f8-115">Il certificato AudioVideoAuthentication precedente rimarrà ancora valido per i token emessi da convalidare.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-115">The older AudioVideoAuthentication certificate will still remain for issued tokens to be validated against.</span></span> <span data-ttu-id="3f1f8-116">A partire dall'immissione del nuovo certificato AudioVideoAuthentication, si verificherà la serie di eventi seguente:</span><span class="sxs-lookup"><span data-stu-id="3f1f8-116">Beginning with putting the new AudioVideoAuthentication certificate in place, the following series of events will occur:</span></span>

<div>


> [!TIP]
> <span data-ttu-id="3f1f8-117">Usando i cmdlet di Lync Server Management Shell per la gestione dei certificati è possibile richiedere certificati distinti e distinti per ogni scopo nell'Edge Server.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-117">Using the Lync Server Management Shell cmdlets for managing certificates, you can request separate and distinct certificates for each purpose on the Edge Server.</span></span> <span data-ttu-id="3f1f8-118">L'uso della creazione guidata certificati nella distribuzione guidata di Lync Server consente di creare certificati, ma in genere è il tipo <STRONG>predefinito</STRONG> per cui tutte le coppie usano tutti i certificati per il server perimetrale su un singolo certificato.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-118">Using the Certificate Wizard in the Lync Server Deployment Wizard assists you in creating certificates, but is typically of the <STRONG>default</STRONG> type which couples all certificate uses for the Edge Server onto a single certificate.</span></span> <span data-ttu-id="3f1f8-119">La procedura consigliata se si vuole usare la caratteristica del certificato rotante consiste nel disaccoppiare il certificato AudioVideoAuthentication dagli altri scopi del certificato.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-119">The recommended practice if you are going to use the rolling certificate feature is to decouple the AudioVideoAuthentication certificate from the other certificate purposes.</span></span> <span data-ttu-id="3f1f8-120">È possibile eseguire il provisioning e la fase di un certificato del tipo predefinito, ma solo la parte AudioVideoAuthentication del certificato combinato trarrà vantaggio dalla gestione temporanea.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-120">You can provision and stage a certificate of the Default type, but only the AudioVideoAuthentication portion of the combined certificate will benefit from the staging.</span></span> <span data-ttu-id="3f1f8-121">Un utente coinvolto (ad esempio) una conversazione di messaggistica istantanea quando il certificato scade deve disconnettersi e accedere nuovamente per usare il nuovo certificato associato al servizio Access Edge.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-121">A user involved in (for example) an instant messaging conversation when the certificate expires will need to log out and log back in to make use of the new certificate associated with the Access Edge service.</span></span> <span data-ttu-id="3f1f8-122">Si verificherà un comportamento simile per un utente coinvolto in una conferenza Web tramite il servizio Web Conferencing Edge.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-122">Similar behavior will occur for a user involved in a Web conference using the Web Conferencing Edge service.</span></span> <span data-ttu-id="3f1f8-123">Il certificato OAuthTokenIssuer è un tipo specifico condiviso in tutti i server.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-123">The OAuthTokenIssuer certificate is a specific type that is shared across all servers.</span></span> <span data-ttu-id="3f1f8-124">Si crea e si gestisce il certificato in un'unica posizione e il certificato viene archiviato in Central Management store per tutti gli altri server.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-124">You create and manage the certificate in one place and the certificate is stored in the Central Management store for all other servers.</span></span>



</div>

<span data-ttu-id="3f1f8-125">È necessario ulteriore dettaglio per comprendere appieno le opzioni e i requisiti quando si usa il cmdlet Set-CsCertificate e usarlo per eseguire la fase dei certificati prima della scadenza del certificato corrente.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-125">Additional detail is needed to fully understand your options and requirements when using the Set-CsCertificate cmdlet and using it to stage certificates prior to the current certificate expiring.</span></span> <span data-ttu-id="3f1f8-126">Il parametro-Roll è importante, ma in sostanza un unico scopo.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-126">The –Roll parameter is important, but essentially single purpose.</span></span> <span data-ttu-id="3f1f8-127">Se lo definisci come parametro, stai dicendo a Set-CsCertificate che ti verranno fornite informazioni sul certificato che sarà influenzato da: tipo (ad esempio AudioVideoAuthentication e OAuthTokenIssuer), quando il certificato diventa efficacia definita da-EffectiveDate.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-127">If you define it as a parameter, you are telling Set-CsCertificate that you will be providing information about the certificate that will be affected defined by –Type (for example AudioVideoAuthentication and OAuthTokenIssuer), when the certificate will become effective defined by –EffectiveDate.</span></span>

<span data-ttu-id="3f1f8-128">**-Roll:** Il parametro-Roll è obbligatorio e contiene le dipendenze che devono essere fornite insieme.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-128">**-Roll:** The –Roll parameter is required and has dependencies that must be supplied along with it.</span></span> <span data-ttu-id="3f1f8-129">Parametri obbligatori per definire completamente quali certificati saranno interessati e come verranno applicati:</span><span class="sxs-lookup"><span data-stu-id="3f1f8-129">Required parameters to fully define which certificates will be affected and how they will be applied:</span></span>

<span data-ttu-id="3f1f8-130">**-EffectiveDate:** Il parametro: EffectiveDate definisce quando il nuovo certificato diventerà coattivo con il certificato corrente.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-130">**-EffectiveDate:** The parameter –EffectiveDate defines when the new certificate will become co-active with the current certificate.</span></span> <span data-ttu-id="3f1f8-131">La – EffectiveDate può essere vicina all'ora di scadenza del certificato corrente o può essere di un periodo di tempo più lungo.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-131">The –EffectiveDate can be close to the expiry time of the current certificate, or it can be a longer period of time.</span></span> <span data-ttu-id="3f1f8-132">Un valore minimo consigliato: EffectiveDate per il certificato AudioVideoAuthentication sarebbe di 8 ore, ovvero la durata del token predefinita per i token del servizio Edge AV emessi con il certificato AudioVideoAuthentication.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-132">A recommended minimum –EffectiveDate for the AudioVideoAuthentication certificate would be 8 hours, which is the default token lifetime for AV Edge service tokens issued using the AudioVideoAuthentication certificate.</span></span>

<span data-ttu-id="3f1f8-133">Quando si verificano i certificati di OAuthTokenIssuer, esistono requisiti diversi per il tempo di anticipo prima che il certificato diventi effettivo.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-133">When staging OAuthTokenIssuer certificates, there are different requirements for the lead time before the certificate can become effective.</span></span> <span data-ttu-id="3f1f8-134">Il tempo minimo che deve avere il certificato OAuthTokenIssuer per il tempo di consegna è 24 ore prima della data di scadenza del certificato corrente.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-134">The minimum time that the OAuthTokenIssuer certificate should have for its lead time is 24 hours before the expiration time of the current certificate.</span></span> <span data-ttu-id="3f1f8-135">Il tempo di esecuzione esteso per la coesistenza è dovuto ad altri ruoli del server che dipendono dal certificato OAuthTokenIssuer (ad esempio, server Exchange) che ha un tempo di conservazione più lungo per l'autenticazione e la chiave di crittografia create da un certificato materiali.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-135">The extended lead time for the coexistence is because of other server roles that are dependent on the OAuthTokenIssuer certificate (Exchange Server, for example) which has a longer retention time for certificate created authentication and encryption key materials.</span></span>

<span data-ttu-id="3f1f8-136">**-Identificazione personale:** L'identificazione personale è un attributo del certificato univoco per tale certificato.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-136">**-Thumbprint:** The thumbprint is an attribute on the certificate that is unique to that certificate.</span></span> <span data-ttu-id="3f1f8-137">Il parametro – identificazione personale viene usato per identificare il certificato che verrà influenzato dalle azioni del cmdlet Set-CsCertificate.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-137">The –Thumbprint parameter is used to identify the certificate that will be affected by the actions of the Set-CsCertificate cmdlet.</span></span>

<span data-ttu-id="3f1f8-138">**-Digitare:** Il parametro-Type può accettare un singolo tipo di utilizzo del certificato o un elenco separato da virgole dei tipi di utilizzo del certificato.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-138">**-Type:** The –Type parameter can accept a single certificate usage type or a comma separated list of certificate usage types.</span></span> <span data-ttu-id="3f1f8-139">I tipi di certificato sono quelli che identificano il cmdlet e al server lo scopo del certificato.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-139">The certificate types are those that identify to the cmdlet and to the server what the purpose of the certificate is.</span></span> <span data-ttu-id="3f1f8-140">Ad esempio, digitare AudioVideoAuthentication per l'uso da parte del servizio A/V Edge e del servizio di autenticazione AV.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-140">For example, type AudioVideoAuthentication is for use by the A/V Edge service and the AV Authentication service.</span></span> <span data-ttu-id="3f1f8-141">Se si decide di eseguire la fase e il provisioning di certificati di un tipo diverso contemporaneamente, è necessario considerare il tempo di anticipo effettivo minimo richiesto per i certificati.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-141">If you decide to stage and provision certificates of a different type at the same time, you must consider the longest required minimum effective lead time for the certificates.</span></span> <span data-ttu-id="3f1f8-142">Ad esempio, è necessario organizzare i certificati di tipo AudioVideoAuthentication e OAuthTokenIssuer.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-142">For example, you need to stage certificates of type AudioVideoAuthentication and OAuthTokenIssuer.</span></span> <span data-ttu-id="3f1f8-143">Il minimo: EffectiveDate deve essere il maggiore dei due certificati, in questo caso OAuthTokenIssuer, che ha un tempo di anticipo minimo di 24 ore.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-143">Your minimum –EffectiveDate must be the greater of the two certificates, in this case the OAuthTokenIssuer, which has a minimum lead time of 24 hours.</span></span> <span data-ttu-id="3f1f8-144">Se non si vuole eseguire la fase di esecuzione del certificato AudioVideoAuthentication con un tempo di anticipo di 24 ore, eseguire la fase separatamente con un EffectiveDate più per le proprie esigenze.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-144">If you do not want to stage the AudioVideoAuthentication certificate with a lead time of 24 hours, stage it separately with an EffectiveDate that is more to your requirements.</span></span>

<div>

## <a name="to-update-or-renew-an-av-edge-service-certificate-with-a-roll-and--effectivedate-parameters"></a><span data-ttu-id="3f1f8-145">Per aggiornare o rinnovare un certificato A/V Edge service con i parametri-roll e-EffectiveDate</span><span class="sxs-lookup"><span data-stu-id="3f1f8-145">To update or renew an A/V Edge service certificate with a –Roll and -EffectiveDate parameters</span></span>

1.  <span data-ttu-id="3f1f8-146">Accedere al computer locale come membro del gruppo Administrators.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-146">Log on to the local computer as a member of the Administrators group.</span></span>

2.  <span data-ttu-id="3f1f8-147">Richiedere un rinnovo o un nuovo certificato AudioVideoAuthentication con la chiave privata esportabile per il certificato esistente nel servizio A/V Edge.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-147">Request a renewal or new AudioVideoAuthentication certificate with exportable private key for the existing certificate on the A/V Edge service.</span></span>

3.  <span data-ttu-id="3f1f8-148">Importare il nuovo certificato AudioVideoAuthentication nel server perimetrale e in tutti gli altri Edge Server nel pool (se è stato distribuito un pool).</span><span class="sxs-lookup"><span data-stu-id="3f1f8-148">Import the new AudioVideoAuthentication certificate to the Edge Server and all other Edge Server in your pool (if you have a pool deployed).</span></span>

4.  <span data-ttu-id="3f1f8-149">Configurare il certificato importato con il cmdlet Set-CsCertificate e usare il parametro – roll con il parametro – EffectiveDate.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-149">Configure the imported certificate with the Set-CsCertificate cmdlet and use the –Roll parameter with the –EffectiveDate parameter.</span></span> <span data-ttu-id="3f1f8-150">La data effettiva deve essere definita come scadenza del certificato corrente (14:00:00 o 2:00:00 PM) meno durata del token (per impostazione predefinita otto ore).</span><span class="sxs-lookup"><span data-stu-id="3f1f8-150">The effective date should be defined as the current certificate expire time (14:00:00, or 2:00:00 PM) minus token lifetime (by default eight hours).</span></span> <span data-ttu-id="3f1f8-151">In questo modo, il certificato deve essere impostato su attivo ed è la stringa \<\>– EFFECTIVEDATE: "7/22/2012 6:00:00 AM".</span><span class="sxs-lookup"><span data-stu-id="3f1f8-151">This gives us a time that the certificate must be set to active, and is the –EffectiveDate \<string\>: “7/22/2012 6:00:00 AM”.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="3f1f8-152">Per un pool di Edge, è necessario disporre di tutti i certificati AudioVideoAuthentication distribuiti e provisionati in base alla data e all'ora definiti dal parametro – EffectiveDate del primo certificato distribuito per evitare possibili interruzioni di comunicazioni a/V a causa del vecchio certificato che scade prima che tutti i client e i token di consumo siano stati rinnovati con il nuovo certificato.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-152">For an Edge pool, you must have all AudioVideoAuthentication certificates deployed and provisioned by the date and time defined by the –EffectiveDate parameter of the first certificate deployed to avoid possible A/V communications disruption due to the older certificate expiring before all client and consumer tokens have been renewed using the new certificate.</span></span>

    
    </div>
    
    <span data-ttu-id="3f1f8-153">Comando Set-CsCertificate con il parametro – roll e – EffectiveTime:</span><span class="sxs-lookup"><span data-stu-id="3f1f8-153">The Set-CsCertificate command with the –Roll and –EffectiveTime parameter:</span></span>
    
        Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint <thumb print of new certificate> -Roll -EffectiveDate <date and time for certificate to become active>
    
    <span data-ttu-id="3f1f8-154">Comando Set-CsCertificate di esempio:</span><span class="sxs-lookup"><span data-stu-id="3f1f8-154">An example Set-CsCertificate command:</span></span>
    
        Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/22/2012 6:00:00 AM"
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="3f1f8-155">EffectiveDate deve essere formattato in base alle impostazioni dell'area geografica e della lingua del server.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-155">The EffectiveDate must be formatted to match your server’s region and language settings.</span></span> <span data-ttu-id="3f1f8-156">Nell'esempio vengono usate le impostazioni della lingua e dell'area inglese degli Stati Uniti</span><span class="sxs-lookup"><span data-stu-id="3f1f8-156">The example uses the US English Region and Language settings</span></span>

    
    </div>

<span data-ttu-id="3f1f8-157">Per comprendere ulteriormente il processo che Set-CsCertificate,-roll e-EffectiveDate USA per creare un nuovo certificato per il rilascio di nuovi token AudioVideoAuthentication mentre si usa ancora un certificato esistente per convalidare AudioVideoAuthentication in uso per i consumatori, una sequenza temporale visiva rappresenta un mezzo efficace per comprendere il processo.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-157">To further understand the process that Set-CsCertificate, -Roll, and –EffectiveDate use to stage a new certificate for issuing new AudioVideoAuthentication tokens while still using an existing certificate to validate AudioVideoAuthentication that are in use by consumers, a visual timeline is an effective means of understanding the process.</span></span>

<span data-ttu-id="3f1f8-158">Nell'esempio seguente l'amministratore determina che il certificato del servizio A/V Edge è scaduto a 2:00:00 PM su 07/22/2012.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-158">In the following example, the administrator determines that the A/V Edge service certificate is due to expire at 2:00:00 PM on 07/22/2012.</span></span> <span data-ttu-id="3f1f8-159">Richiede e riceve un nuovo certificato e lo importa in ogni Edge Server nel suo pool.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-159">He requests and receives a new certificate and imports it to each Edge Server in his pool.</span></span> <span data-ttu-id="3f1f8-160">Alle 2 di 07/22/2012, inizia a eseguire Get-CsCertificate con-roll,-identificazione personale uguale alla stringa di identificazione personale del nuovo certificato e-EffectiveTime impostato su 07/22/2012 6:00:00 AM.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-160">At 2 AM on 07/22/2012, he begins running Get-CsCertificate with –Roll, -Thumbprint equal to the thumbprint string of the new certificate, and –EffectiveTime set to 07/22/2012 6:00:00 AM.</span></span> <span data-ttu-id="3f1f8-161">Esegue questo comando in ogni server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-161">He runs this command on each Edge Server.</span></span>

<span data-ttu-id="3f1f8-162">![Uso dei parametri roll e EffectiveDate.] (images/JJ660292.21d51a76-0d03-4ed7-a37e-a7c14940265f(OCS.15).jpg "Uso dei parametri roll e EffectiveDate.")</span><span class="sxs-lookup"><span data-stu-id="3f1f8-162">![Using the Roll and the EffectiveDate parameters.](images/JJ660292.21d51a76-0d03-4ed7-a37e-a7c14940265f(OCS.15).jpg "Using the Roll and the EffectiveDate parameters.")</span></span>

<span data-ttu-id="3f1f8-163">Quando viene raggiunto il tempo effettivo (7/22/2012 6:00:00 AM), tutti i nuovi token vengono emessi dal nuovo certificato.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-163">When the effective time is reached (7/22/2012 6:00:00 AM), all new tokens are issued by the new certificate.</span></span> <span data-ttu-id="3f1f8-164">Quando si convalidano i token, i token verranno prima convalidati in base al nuovo certificato.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-164">When validating tokens, tokens will first be validated against the new certificate.</span></span> <span data-ttu-id="3f1f8-165">Se la convalida non riesce, viene provato il vecchio certificato.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-165">If the validation fails, the old certificate is tried.</span></span> <span data-ttu-id="3f1f8-166">Il processo per provare il nuovo e il ritorno al vecchio certificato continuerà fino all'ora di scadenza del vecchio certificato.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-166">The process of trying the new and falling back to the old certificate will continue until the expiry time of the old certificate.</span></span> <span data-ttu-id="3f1f8-167">Dopo la scadenza del certificato precedente (7/22/2012 2:00:00 PM), i token verranno convalidati solo dal nuovo certificato.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-167">Once the old certificate has expired (7/22/2012 2:00:00 PM), tokens will only be validated by the new certificate.</span></span> <span data-ttu-id="3f1f8-168">Il vecchio certificato può essere rimosso in modo sicuro usando il cmdlet Remove-CsCertificate con il parametro – Previous.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-168">The old certificate can be safely removed using the Remove-CsCertificate cmdlet with the –Previous parameter.</span></span>

    Remove-CsCertificate -Type AudioVideoAuthentication -Previous

</div>

<div>

## <a name="to-update-or-renew-an-oauthtokenissuer-certificate-with-a-roll-and--effectivedate-parameters"></a><span data-ttu-id="3f1f8-169">Per aggiornare o rinnovare un certificato OAuthTokenIssuer con i parametri-roll e-EffectiveDate</span><span class="sxs-lookup"><span data-stu-id="3f1f8-169">To update or renew an OAuthTokenIssuer certificate with a –Roll and -EffectiveDate parameters</span></span>

1.  <span data-ttu-id="3f1f8-170">Accedere al computer locale come membro del gruppo Administrators.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-170">Log on to the local computer as a member of the Administrators group.</span></span>

2.  <span data-ttu-id="3f1f8-171">Richiedere un rinnovo o un nuovo certificato OAuthTokenIssuer con la chiave privata esportabile per il certificato esistente nel servizio A/V Edge.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-171">Request a renewal or new OAuthTokenIssuer certificate with exportable private key for the existing certificate on the A/V Edge service.</span></span>

3.  <span data-ttu-id="3f1f8-172">Importare il nuovo certificato OAuthTokenIssuer in un server front-end nel pool (se è stato distribuito un pool).</span><span class="sxs-lookup"><span data-stu-id="3f1f8-172">Import the new OAuthTokenIssuer certificate to a Front End Server in your pool (if you have a pool deployed).</span></span> <span data-ttu-id="3f1f8-173">Il certificato OAuthTokenIssuer viene replicato globalmente e deve essere aggiornato e rinnovato solo in qualsiasi server della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-173">The OAuthTokenIssuer certificate is replicated globally and only needs to be updated and renewed at any server in your deployment.</span></span> <span data-ttu-id="3f1f8-174">Il server front-end viene usato come esempio.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-174">The Front End Server is used as an example.</span></span>

4.  <span data-ttu-id="3f1f8-175">Configurare il certificato importato con il cmdlet Set-CsCertificate e usare il parametro – roll con il parametro – EffectiveDate.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-175">Configure the imported certificate with the Set-CsCertificate cmdlet and use the –Roll parameter with the –EffectiveDate parameter.</span></span> <span data-ttu-id="3f1f8-176">La data effettiva deve essere definita come il periodo di scadenza del certificato corrente (14:00:00 o 2:00:00 PM) meno un minimo di 24 ore.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-176">The effective date should be defined as the current certificate expire time (14:00:00, or 2:00:00 PM) minus a minimum of 24 hours.</span></span>
    
    <span data-ttu-id="3f1f8-177">Comando Set-CsCertificate con il parametro – roll e – EffectiveTime:</span><span class="sxs-lookup"><span data-stu-id="3f1f8-177">The Set-CsCertificate command with the –Roll and –EffectiveTime parameter:</span></span>
    
        Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint <thumb print of new certificate> -Roll -EffectiveDate <date and time for certificate to become active>
    
    <span data-ttu-id="3f1f8-178">Comando Set-CsCertificate di esempio:</span><span class="sxs-lookup"><span data-stu-id="3f1f8-178">An example Set-CsCertificate command:</span></span>
    
        Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/21/2012 1:00:00 PM"
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="3f1f8-179">EffectiveDate deve essere formattato in base alle impostazioni dell'area geografica e della lingua del server.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-179">The EffectiveDate must be formatted to match your server’s region and language settings.</span></span> <span data-ttu-id="3f1f8-180">Nell'esempio vengono usate le impostazioni della lingua e dell'area inglese degli Stati Uniti</span><span class="sxs-lookup"><span data-stu-id="3f1f8-180">The example uses the US English Region and Language settings</span></span>

    
    </div>

<span data-ttu-id="3f1f8-181">Quando viene raggiunto il tempo effettivo (7/21/2012 1:00:00 AM), tutti i nuovi token vengono emessi dal nuovo certificato.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-181">When the effective time is reached (7/21/2012 1:00:00 AM), all new tokens are issued by the new certificate.</span></span> <span data-ttu-id="3f1f8-182">Quando si convalidano i token, i token verranno prima convalidati in base al nuovo certificato.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-182">When validating tokens, tokens will first be validated against the new certificate.</span></span> <span data-ttu-id="3f1f8-183">Se la convalida non riesce, viene provato il vecchio certificato.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-183">If the validation fails, the old certificate is tried.</span></span> <span data-ttu-id="3f1f8-184">Il processo per provare il nuovo e il ritorno al vecchio certificato continuerà fino all'ora di scadenza del vecchio certificato.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-184">The process of trying the new and falling back to the old certificate will continue until the expiry time of the old certificate.</span></span> <span data-ttu-id="3f1f8-185">Dopo la scadenza del certificato precedente (7/22/2012 2:00:00 PM), i token verranno convalidati solo dal nuovo certificato.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-185">Once the old certificate has expired (7/22/2012 2:00:00 PM), tokens will only be validated by the new certificate.</span></span> <span data-ttu-id="3f1f8-186">Il vecchio certificato può essere rimosso in modo sicuro usando il cmdlet Remove-CsCertificate con il parametro – Previous.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-186">The old certificate can be safely removed using the Remove-CsCertificate cmdlet with the –Previous parameter.</span></span>

    Remove-CsCertificate -Type OAuthTokenIssuer -Previous

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3f1f8-187">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3f1f8-187">See Also</span></span>


[<span data-ttu-id="3f1f8-188">Pianificare i certificati dei server perimetrali in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3f1f8-188">Plan for Edge Server certificates in Lync Server 2013</span></span>](lync-server-2013-plan-for-edge-server-certificates.md)  
[<span data-ttu-id="3f1f8-189">Gestione dell'autenticazione server-Server (OAuth) e delle applicazioni partner in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3f1f8-189">Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013</span></span>](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)  


[<span data-ttu-id="3f1f8-190">Configurare i certificati perimetrali per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3f1f8-190">Set up Edge certificates for Lync Server 2013</span></span>](lync-server-2013-set-up-edge-certificates.md)  
<span data-ttu-id="3f1f8-191">[Set-CsCertificate](https://technet.microsoft.com/en-us/library/Gg398518(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3f1f8-191">[Set-CsCertificate](https://technet.microsoft.com/en-us/library/Gg398518(v=OCS.15))</span></span>  
<span data-ttu-id="3f1f8-192">[Remove-CsCertificate](https://technet.microsoft.com/en-us/library/Gg412895(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="3f1f8-192">[Remove-CsCertificate](https://technet.microsoft.com/en-us/library/Gg412895(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

