---
title: Come vengono visualizzate le foto degli utenti in Lync
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: How user photos are displayed in Lync
ms:assetid: b44a364d-a1d2-4d45-b27a-b5f77775e233
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn783119(v=OCS.15)
ms:contentKeyID: 62835297
ms.date: 08/27/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ac13f066c24f66640aee1360caf1d341d604474
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40979624"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="how-user-photos-are-displayed-in-lync"></a><span data-ttu-id="34654-102">Come vengono visualizzate le foto degli utenti in Lync</span><span class="sxs-lookup"><span data-stu-id="34654-102">How user photos are displayed in Lync</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="34654-103">_**Argomento Ultima modifica:** 2014-08-25_</span><span class="sxs-lookup"><span data-stu-id="34654-103">_**Topic Last Modified:** 2014-08-25_</span></span>

<span data-ttu-id="34654-104">**Riepilogo:** Le foto degli utenti visualizzate nel client Lync possono variare a seconda della funzionalità di Lync in uso, ad esempio in una conferenza o in una chat di messaggistica istantanea.</span><span class="sxs-lookup"><span data-stu-id="34654-104">**Summary:** User photos displayed in Lync client can be different depending on which Lync feature you are using, such as when in a conference or an IM chat.</span></span>

<span data-ttu-id="34654-105">Lync 2010 ha introdotto la possibilità di includere una foto con il proprio profilo Lync che viene visualizzato ad altri utenti di Lync.</span><span class="sxs-lookup"><span data-stu-id="34654-105">Lync 2010 introduced the ability to include a photo with your Lync profile that is displayed to other Lync users.</span></span> <span data-ttu-id="34654-106">È anche possibile scegliere se visualizzare o meno le foto per i contatti nel client Lync.</span><span class="sxs-lookup"><span data-stu-id="34654-106">You can also choose whether or not to display photos for your contacts in Lync client.</span></span> <span data-ttu-id="34654-107">In Lync 2013 è supportato il supporto per le foto ad alta risoluzione per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="34654-107">In Lync 2013, support for high-resolution photos for users.</span></span> <span data-ttu-id="34654-108">Questo argomento descrive il modo in cui il client Lync viene visualizzato e visualizza le foto degli utenti, in cui sono archiviate le immagini, le limitazioni per ogni origine di immagine e la modalità di utilizzo delle foto degli utenti da servizi Lync diversi.</span><span class="sxs-lookup"><span data-stu-id="34654-108">This topic describes how Lync client gets and displays user photos, where the images are stored, the limitations for each image source, and how user photos are used by different Lync services.</span></span>

<div>

## <a name="planning-considerations"></a><span data-ttu-id="34654-109">Considerazioni sulla pianificazione</span><span class="sxs-lookup"><span data-stu-id="34654-109">Planning considerations</span></span>

<span data-ttu-id="34654-110">Quando si pianifica di implementare il supporto per le foto degli utenti, tenere presente quanto segue.</span><span class="sxs-lookup"><span data-stu-id="34654-110">You should consider the following when planning to implement support for user photos.</span></span>

  - <span data-ttu-id="34654-111">Il supporto per le foto degli utenti ad alta definizione richiede che la cassetta postale dell'utente si trovi in Exchange 2013 e che l'account utente di Lync sia in Lync 2013 pool.</span><span class="sxs-lookup"><span data-stu-id="34654-111">High-definition user photo support requires that the user’s mailbox be located on Exchange 2013 and the Lync user account to be in Lync 2013 pool.</span></span>

  - <span data-ttu-id="34654-112">Le foto degli utenti ad alta definizione sono supportate solo in un ambiente in cui vengono usati sia Lync Server 2013 che Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="34654-112">High-definition user photos are supported only in an environment where both Lync Server 2013 and Exchange 2013 are used.</span></span>

  - <span data-ttu-id="34654-113">Gli utenti con cassette postali in Exchange 2010 utilizzeranno sempre l'attributo **ThumbNailPhoto** di servizi di dominio Active Directory come origine per la propria foto utente.</span><span class="sxs-lookup"><span data-stu-id="34654-113">Users with Mailboxes on Exchange 2010 will always use the **thumbnailPhoto** attribute from AD DS as the source for their user photo.</span></span>

  - <span data-ttu-id="34654-114">Una foto utente archiviata come attributo **ThumbNailPhoto** da servizi di dominio Active Directory non verrà visualizzata per i contatti esterni/federati.</span><span class="sxs-lookup"><span data-stu-id="34654-114">A user photo stored as the **thumbnailPhoto** attribute from AD DS will not be displayed to external / federated contacts.</span></span>

  - <span data-ttu-id="34654-115">Se le foto per i contatti utente sono archiviate in servizi di dominio Active Directory, il file di immagine usato è limitato a 96 × 96 pixel e non supera le dimensioni del file di 100 KB.</span><span class="sxs-lookup"><span data-stu-id="34654-115">If the photos for user contacts are stored in AD DS, the image file used is limited to 96×96 pixels and no more than 100 KB file size.</span></span>

  - <span data-ttu-id="34654-116">Se si perde la connettività tra Lync Server ed Exchange Server, viene visualizzato il **ThumbNailPhoto** a bassa risoluzione dell'utente da servizi di dominio Active Directory e solo agli utenti interni.</span><span class="sxs-lookup"><span data-stu-id="34654-116">If connectivity between Lync Server and Exchange Server is lost, the user’s low resolution **thumbnailPhoto** from AD DS will be displayed, and to internal users only.</span></span>

  - <span data-ttu-id="34654-117">Le foto degli utenti ad alta risoluzione vengono visualizzate nelle riunioni di Lync 2013 quando un altoparlante attivo non è abilitato per il video.</span><span class="sxs-lookup"><span data-stu-id="34654-117">High-resolution user photos are displayed in Lync 2013 meetings when an active speaker does not have video enabled.</span></span> <span data-ttu-id="34654-118">Inoltre, spostando il mouse sulla foto in anteprima nella raccolta verrà visualizzata la foto ad alta risoluzione.</span><span class="sxs-lookup"><span data-stu-id="34654-118">Also, moving the mouse over thumbnail photo in the gallery will display the high-resolution photo.</span></span>

</div>

<div>

## <a name="user-photos-in-lync-2010"></a><span data-ttu-id="34654-119">Foto degli utenti in Lync 2010</span><span class="sxs-lookup"><span data-stu-id="34654-119">User Photos in Lync 2010</span></span>

<span data-ttu-id="34654-120">Nel client Lync 2010 è possibile scegliere tra due opzioni per visualizzare una foto per il profilo, l' **immagine aziendale predefinita** e la visualizzazione **dell'immagine da un indirizzo Web**.</span><span class="sxs-lookup"><span data-stu-id="34654-120">In the Lync 2010 client, you can choose from two options to display a photo for your profile, **Default corporate picture** and **Show picture from a web address**.</span></span>

<div>

## <a name="default-corporate-picture"></a><span data-ttu-id="34654-121">Immagine aziendale predefinita</span><span class="sxs-lookup"><span data-stu-id="34654-121">Default corporate picture</span></span>

<span data-ttu-id="34654-122">Quando si sceglie l'opzione **immagine aziendale predefinita** , Lync riceve la foto visualizzata da servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="34654-122">When you choose the **Default corporate picture** option, Lync gets the photo displayed for you from Active Directory Domain Services.</span></span> <span data-ttu-id="34654-123">L'immagine usata è l'immagine definita come valore per l'attributo **ThumbNailPhoto** in servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="34654-123">The image used is the image defined as the value for the **thumbnailPhoto** attribute in Active Directory Domain Services.</span></span> <span data-ttu-id="34654-124">Si tratta dello stesso file usato da Exchange per visualizzare le immagini in Outlook.</span><span class="sxs-lookup"><span data-stu-id="34654-124">This is the same file that is used by Exchange to display images in Outlook.</span></span>

<span data-ttu-id="34654-125">Le considerazioni relative all'uso di immagini da servizi di dominio Active Directory includono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="34654-125">Considerations for using images from Active Directory Domain Services include the following:</span></span>

  - <span data-ttu-id="34654-126">Sono supportate solo le immagini con dimensioni fino a 96 pixel per 96 pixel.</span><span class="sxs-lookup"><span data-stu-id="34654-126">Only images with dimensions up to 96 pixels by 96 pixels are supported.</span></span> <span data-ttu-id="34654-127">Le dimensioni del file per l'immagine sono limitate a 100 KB.</span><span class="sxs-lookup"><span data-stu-id="34654-127">The file size for the image is limited to 100 KB.</span></span>

  - <span data-ttu-id="34654-128">Per impostazione predefinita, gli utenti possono modificare l'immagine usata per l'attributo **ThumbNailPhoto** , anche se non direttamente tramite client Lync.</span><span class="sxs-lookup"><span data-stu-id="34654-128">By default, users are able to change the image used for the **thumbnailPhoto** attribute, though not directly through Lync client.</span></span> <span data-ttu-id="34654-129">Puoi disabilitare questa operazione tramite servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="34654-129">You can disable this through Active Directory Domain Services.</span></span>

  - <span data-ttu-id="34654-130">Le immagini archiviate in servizi di dominio Active Directory non vengono visualizzate ai contatti esterni all'organizzazione, anche se sono contatti federati.</span><span class="sxs-lookup"><span data-stu-id="34654-130">Images stored in Active Directory Domain Services are not displayed to contacts external to your organization, even if they are federated contacts.</span></span>

  - <span data-ttu-id="34654-131">Nelle organizzazioni di grandi dimensioni, l'archiviazione e il recupero delle immagini per un numero elevato di utenti possono influire sulle dimensioni e sulle prestazioni del database dei servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="34654-131">In large organizations, storing and retrieving the images for large numbers of users may impact the Active Directory Domain Services database size and performance.</span></span>

  - <span data-ttu-id="34654-132">Le dimensioni limitate delle immagini e le dimensioni dei file indicano che possono essere usate solo immagini a bassa risoluzione.</span><span class="sxs-lookup"><span data-stu-id="34654-132">The limited image dimensions and file size mean that only low resolution images can be used.</span></span>

<div>

## <a name="how-users-manage-their-user-photos-in-active-directory-domain-services"></a><span data-ttu-id="34654-133">Modalità di gestione delle foto degli utenti in servizi di dominio Active Directory</span><span class="sxs-lookup"><span data-stu-id="34654-133">How users manage their user photos in Active Directory Domain Services</span></span>

<span data-ttu-id="34654-134">L'utente non può modificare l'immagine usata nel profilo dei servizi di dominio Active Directory direttamente tramite il client Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="34654-134">User cannot change the image used in their Active Directory Domain Services profile directly through Lync 2010 client.</span></span> <span data-ttu-id="34654-135">Possono usare una delle opzioni seguenti per eseguire questa operazione, se disponibile:</span><span class="sxs-lookup"><span data-stu-id="34654-135">They can use one of the following options to do so, if available:</span></span>

  - <span data-ttu-id="34654-136">\*\*\*\*   Gli utenti di SharePoint Server possono caricare una foto in "sito personale" in un server di SharePoint e quindi [configurare la sincronizzazione del profilo in SharePoint](http://go.microsoft.com/fwlink/p/?linkid=507466) per sincronizzare la foto con l'attributo **ThumbNailPhoto** in servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="34654-136">**SharePoint Server**   Users can upload a photo to ‘My Site’ on a SharePoint Server and then [configure profile synchronization in SharePoint](http://go.microsoft.com/fwlink/p/?linkid=507466) to synchronize the photo to the **thumbnailPhoto** attribute in Active Directory Domain Services.</span></span>

  - <span data-ttu-id="34654-137">**Foto archiviate in URL**   accessibili pubblicamente gli utenti possono configurare la propria foto utente specificando un URL accessibile pubblicamente per l'immagine che vuole usare.</span><span class="sxs-lookup"><span data-stu-id="34654-137">**Photo stored on publicly accessible URL**   Users can configure their user photo specifying a publicly accessible URL for the image that they want to use.</span></span> <span data-ttu-id="34654-138">L'immagine deve essere pubblicamente accessibile senza una password.</span><span class="sxs-lookup"><span data-stu-id="34654-138">The image must be publicly accessible without a password.</span></span> <span data-ttu-id="34654-139">L'immagine archiviata presso l'indirizzo Web specificato viene trasferita ad altri utenti tramite la categoria della scheda contatto nelle informazioni sulla presenza.</span><span class="sxs-lookup"><span data-stu-id="34654-139">The image stored at the specified web address is transferred to other users through the contact card category in the presence information.</span></span> <span data-ttu-id="34654-140">Quando il client Lync deve visualizzare una foto utente, recupera l'immagine dall'indirizzo Web specificato.</span><span class="sxs-lookup"><span data-stu-id="34654-140">When Lync client needs to display a user photo, it retrieves the image from the specified web address.</span></span>

  - <span data-ttu-id="34654-141">**I cmdlet di Exchange 2010 per gli amministratori di Windows PowerShell**   possono eseguire il cmdlet [Import-RecipientDataProperty](http://go.microsoft.com/fwlink/p/?linkid=507468) in Exchange 2010 Management Shell in per gestire l'attributo **ThumbNailPhoto** .</span><span class="sxs-lookup"><span data-stu-id="34654-141">**Exchange 2010 cmdlets for Windows PowerShell**   Administrators can run the [Import-RecipientDataProperty](http://go.microsoft.com/fwlink/p/?linkid=507468) cmdlet in the Exchange 2010 Management Shell in to manage the **thumbnailPhoto** attribute.</span></span> <span data-ttu-id="34654-142">Quando le immagini vengono importate con i cmdlet di Exchange 2010, la dimensione del file è limitata a 10 KB.</span><span class="sxs-lookup"><span data-stu-id="34654-142">When images are imported with Exchange 2010 cmdlets, the file size is limited to 10 KB.</span></span>

  - <span data-ttu-id="34654-143">**Strumenti di terze parti**   gli utenti possono caricare solo la propria foto per l'attributo **ThumbNailPhoto** .</span><span class="sxs-lookup"><span data-stu-id="34654-143">**Third Party tools**   Users can upload only their own photo to for the **thumbnailPhoto** attribute.</span></span>

</div>

</div>

<div>

## <a name="show-a-picture-from-a-web-address"></a><span data-ttu-id="34654-144">Visualizzare un'immagine da un indirizzo Web</span><span class="sxs-lookup"><span data-stu-id="34654-144">Show a picture from a web address</span></span>

<span data-ttu-id="34654-145">Quando si sceglie l'opzione **Mostra un'immagine da un indirizzo Web** , Lync ottiene l'immagine all'indirizzo immesso e la Visualizza per la foto dell'utente in Lync.</span><span class="sxs-lookup"><span data-stu-id="34654-145">When you choose the **Show a picture from a web address** option, Lync gets the image at the address you enter and displays it for your user photo in Lync.</span></span>

<span data-ttu-id="34654-146">Le considerazioni relative all'uso di immagini da un indirizzo Web includono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="34654-146">Considerations for using images from a web address include the following:</span></span>

  - <span data-ttu-id="34654-147">I limiti delle dimensioni dei file sono determinati dall'attributo **MaxPhotoSizeKB** nel criterio client, definito con il cmdlet [New-CsClientPolicy](http://go.microsoft.com/fwlink/p/?linkid=507463) .</span><span class="sxs-lookup"><span data-stu-id="34654-147">File size limits are determined by the **MaxPhotoSizeKB** attribute in the client policy, defined with the [New-CsClientPolicy](http://go.microsoft.com/fwlink/p/?linkid=507463) cmdlet.</span></span> <span data-ttu-id="34654-148">Il limite di dimensione predefinito è di 30 KB.</span><span class="sxs-lookup"><span data-stu-id="34654-148">The default size limit is 30 KB.</span></span> <span data-ttu-id="34654-149">Il valore massimo è 100 KB.</span><span class="sxs-lookup"><span data-stu-id="34654-149">The maximum value is 100 KB.</span></span> <span data-ttu-id="34654-150">Non esiste alcuna restrizione per la risoluzione dell'immagine, ma se si prova a usare un file di immagine che supera il limite di dimensioni non verrà scaricato nei client Lync.</span><span class="sxs-lookup"><span data-stu-id="34654-150">There is no restriction on the resolution of the image, but if you try to use an image file that exceeds the size limit it will not be downloaded to Lync clients.</span></span> <span data-ttu-id="34654-151">Puoi impostare il valore su 0 per disabilitare l'uso di tutte le foto degli utenti in Lync.</span><span class="sxs-lookup"><span data-stu-id="34654-151">You can set the value to 0 to disable all user photos from being used in Lync.</span></span>

  - <span data-ttu-id="34654-152">Le foto degli utenti da un indirizzo Web possono essere visualizzate da contatti federati esterni.</span><span class="sxs-lookup"><span data-stu-id="34654-152">User photos from a web address can be seen by external federated contacts.</span></span>

</div>

<div>

## <a name="managing-users-photo-with-client-policy-cmdlets"></a><span data-ttu-id="34654-153">Gestione della foto dell'utente con i cmdlet dei criteri client</span><span class="sxs-lookup"><span data-stu-id="34654-153">Managing user’s photo with Client Policy cmdlets</span></span>

<span data-ttu-id="34654-154">In Lync Server 2010 le impostazioni dei criteri client sono configurate con i cmdlet CsClientPolicy.</span><span class="sxs-lookup"><span data-stu-id="34654-154">In Lync Server 2010, client policy settings are configured with the CsClientPolicy cmdlets.</span></span> <span data-ttu-id="34654-155">Le impostazioni dei criteri configurate vengono inviate ai client tramite il provisioning in banda.</span><span class="sxs-lookup"><span data-stu-id="34654-155">The configured policy settings are sent to clients through in-band provisioning.</span></span> <span data-ttu-id="34654-156">I due parametri dei cmdlet CsClientPolicy che determinano l'esperienza di foto utente sono **DisplayPhoto** e **MaxPhotoSizeKB**.</span><span class="sxs-lookup"><span data-stu-id="34654-156">The two parameters of the CsClientPolicy cmdlets that determine the user photo experience are **DisplayPhoto** and **MaxPhotoSizeKB**.</span></span> <span data-ttu-id="34654-157">Il parametro di provisioning in banda corrispondente per **DisplayPhoto** e **MaxPhotoSizeKB** è denominato **fotoutilizzo**.</span><span class="sxs-lookup"><span data-stu-id="34654-157">The corresponding in-band provisioning parameter for **DisplayPhoto** and **MaxPhotoSizeKB** is named **PhotoUsage**.</span></span> <span data-ttu-id="34654-158">I valori per il parametro di **fotoutilizzo** vengono inviati ai client tramite la **provisionGroup** **EndpointConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="34654-158">Values for the **PhotoUsage** parameter are send to clients through the **endpointConfiguration** **provisionGroup**.</span></span> <span data-ttu-id="34654-159">Per altre informazioni, vedere [Panoramica dei criteri e delle impostazioni client](http://go.microsoft.com/fwlink/?linkid=507470) .</span><span class="sxs-lookup"><span data-stu-id="34654-159">See [Overview of Client Policies and Settings](http://go.microsoft.com/fwlink/?linkid=507470) for more information.</span></span>

<span data-ttu-id="34654-160">Il valore del parametro **DisplayPhoto** determina l'origine dell'immagine della foto dell'utente.</span><span class="sxs-lookup"><span data-stu-id="34654-160">The **DisplayPhoto** parameter value determines the source of the user's photo image.</span></span> <span data-ttu-id="34654-161">I valori supportati sono inclusi nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="34654-161">The supported values are included in the following table.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="34654-162">Valore del parametro DisplayPhoto</span><span class="sxs-lookup"><span data-stu-id="34654-162">DisplayPhoto parameter value</span></span></th>
<th><span data-ttu-id="34654-163">Origine immagini</span><span class="sxs-lookup"><span data-stu-id="34654-163">Image source</span></span></th>
<th><span data-ttu-id="34654-164">Impostazioni client di Lync 2010</span><span class="sxs-lookup"><span data-stu-id="34654-164">Lync 2010 client settings</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="34654-165">Nophoto</span><span class="sxs-lookup"><span data-stu-id="34654-165">NoPhoto</span></span></p></td>
<td><p><span data-ttu-id="34654-166">nessuno</span><span class="sxs-lookup"><span data-stu-id="34654-166">none</span></span></p></td>
<td><p><span data-ttu-id="34654-167"><strong>Non mostrare l'immagine personale</strong></span><span class="sxs-lookup"><span data-stu-id="34654-167"><strong>Do not show my picture</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34654-168">PhotoFromADOnly</span><span class="sxs-lookup"><span data-stu-id="34654-168">PhotoFromADOnly</span></span></p></td>
<td><p><span data-ttu-id="34654-169">Active Directory</span><span class="sxs-lookup"><span data-stu-id="34654-169">Active Directory</span></span></p></td>
<td><p><span data-ttu-id="34654-170"><strong>Immagine aziendale predefinita</strong></span><span class="sxs-lookup"><span data-stu-id="34654-170"><strong>Default corporate picture</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34654-171">AllPhotos</span><span class="sxs-lookup"><span data-stu-id="34654-171">AllPhotos</span></span></p></td>
<td><p><span data-ttu-id="34654-172">Indirizzo Web</span><span class="sxs-lookup"><span data-stu-id="34654-172">Web address</span></span></p></td>
<td><p><span data-ttu-id="34654-173"><strong>Visualizzare un'immagine da un indirizzo Web</strong></span><span class="sxs-lookup"><span data-stu-id="34654-173"><strong>Show a picture from a web address</strong></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="how-lync-2010-client-gets-photos"></a><span data-ttu-id="34654-174">Come il client Lync 2010 ottiene le foto</span><span class="sxs-lookup"><span data-stu-id="34654-174">How Lync 2010 client gets photos</span></span>

<span data-ttu-id="34654-175">In Lync 2010 le foto degli utenti vengono gestite dal server tramite il servizio Rubrica.</span><span class="sxs-lookup"><span data-stu-id="34654-175">In Lync 2010, user photos are managed on the server by the Address Book Service.</span></span> <span data-ttu-id="34654-176">Il client Lync riceve le foto degli utenti prima di eseguire una query sul servizio query Web della Rubrica (ABWQ) nel server, esposto tramite il servizio Web di espansione della lista di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="34654-176">Lync client gets user photos by first querying the Address Book Web Query (ABWQ) service on the server, which is exposed through the Distribution List Expansion web service.</span></span> <span data-ttu-id="34654-177">Il client riceve il file di immagine e lo copia nella cache dell'utente per evitare di scaricare l'immagine ogni volta che deve essere visualizzata.</span><span class="sxs-lookup"><span data-stu-id="34654-177">The client receives the image file and then copies it to the user's cache to avoid downloading the image each time it needs to be displayed.</span></span> <span data-ttu-id="34654-178">I valori di attributo restituiti dalla query vengono archiviati anche nella voce del servizio rubrica memorizzata nella cache per l'utente.</span><span class="sxs-lookup"><span data-stu-id="34654-178">The attribute values returned from the query are also stored in the cached Address Book Service entry for the user.</span></span> <span data-ttu-id="34654-179">Il servizio Rubrica Elimina tutte le immagini memorizzate nella cache ogni 24 ore, quindi può richiedere fino a 24 ore affinché le nuove immagini degli utenti vengano aggiornate nella cache del server.</span><span class="sxs-lookup"><span data-stu-id="34654-179">The Address Book Service deletes all cached images every 24 hours, which means that it can take up to 24 hours for new user images to be updated in the cache on the server.</span></span> <span data-ttu-id="34654-180">Puoi forzare un aggiornamento alla cache usando il cmdlet [Update-CsAddressBook](https://docs.microsoft.com/powershell/module/skype/Update-CsAddressBook) .</span><span class="sxs-lookup"><span data-stu-id="34654-180">You can force an update to the cache by using the [Update-CsAddressBook](https://docs.microsoft.com/powershell/module/skype/Update-CsAddressBook) cmdlet.</span></span>

<span data-ttu-id="34654-181">Le foto utente incluse nello stato presenza hanno anche un valore hash associato che il client Lync USA per determinare se è disponibile un'immagine più recente.</span><span class="sxs-lookup"><span data-stu-id="34654-181">User photos included in Presence status also have an associated hash value that Lync client uses to determine whether there is a newer image available.</span></span> <span data-ttu-id="34654-182">Il client riceve automaticamente una notifica delle modifiche apportate al file di immagine usato nello stato presenza.</span><span class="sxs-lookup"><span data-stu-id="34654-182">The client is automatically notified of changes to the image file used in Presence status.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="34654-183">Poiché le foto non sono archiviate nel database GalContacts. DB, il download delle foto utente non dipende dall'impostazione <STRONG>AddressBookAvailability</STRONG> nel criterio client (<A href="http://go.microsoft.com/fwlink/p/?linkid=507508">Set-CsClientPolicy</A>).</span><span class="sxs-lookup"><span data-stu-id="34654-183">Because photos are not stored in the GalContacts.db database, downloading user photos is not dependent on the <STRONG>AddressBookAvailability</STRONG> setting in the client policy (<A href="http://go.microsoft.com/fwlink/p/?linkid=507508">Set-CsClientPolicy</A>).</span></span>



</div>

<span data-ttu-id="34654-184">La query al servizio ABWQ include gli attributi seguenti:</span><span class="sxs-lookup"><span data-stu-id="34654-184">The query to the ABWQ service includes the following attributes:</span></span>

  - <span data-ttu-id="34654-185">**Fotohash**   il valore hash dei dati di foto binari e viene usato per determinare se la foto corrente è cambiata.</span><span class="sxs-lookup"><span data-stu-id="34654-185">**PhotoHash**   The hash value of the binary photo data, and is used to determine whether the current photo has changed.</span></span>

  - <span data-ttu-id="34654-186">**PhotoRelPath**   il percorso relativo al file di immagine archiviato nel server.</span><span class="sxs-lookup"><span data-stu-id="34654-186">**PhotoRelPath**   The relative path to the image file stored on the server.</span></span>

  - <span data-ttu-id="34654-187">**Ridimensionare le dimensioni**   del file di immagine in byte.</span><span class="sxs-lookup"><span data-stu-id="34654-187">**PhotoSize**   The size of the image file, in bytes.</span></span>

  - <span data-ttu-id="34654-188">**TimeStamp**   la data e l'ora in cui il file di immagine è stato scaricato l'ultima volta dal server e copiato nella cache del client.</span><span class="sxs-lookup"><span data-stu-id="34654-188">**TimeStamp**   The date and time at which the image file was last downloaded from the server and copied to the client cache.</span></span>

<span data-ttu-id="34654-189">Dopo aver recuperato il file di immagine, il client Lync 2010 confronta i valori degli attributi restituiti dalla query in base ai valori degli attributi ricevuti dal client da provisioning in banda per verificare se sono diversi.</span><span class="sxs-lookup"><span data-stu-id="34654-189">Next, after retrieving the image file, Lync 2010 client compares the attribute values returned from the query against the attribute values received by the client from in-band provisioning to see if they are different.</span></span> <span data-ttu-id="34654-190">Se i valori sono diversi, il client recupera il file di immagine dell'utente connesso con una richiesta HTTP GET.</span><span class="sxs-lookup"><span data-stu-id="34654-190">If the values are different, the client retrieves the image file of the signed-in user with an HTTP GET request.</span></span>

<span data-ttu-id="34654-191">Inoltre, il client controlla con il server ogni 24 ore dall'ora in cui è stata creata la versione memorizzata nella cache del file di immagine per confrontare il valore dell'attributo **fotohash** nel server con il valore sul client.</span><span class="sxs-lookup"><span data-stu-id="34654-191">Additionally, the client checks with the server every 24 hours from the time at which the cached version of the image file was created to compare the value of the **PhotoHash** attribute on the server with the value on the client.</span></span> <span data-ttu-id="34654-192">Se i valori sono diversi, il client sa che il file di immagine è cambiato.</span><span class="sxs-lookup"><span data-stu-id="34654-192">If the values are different, the client knows that the image file has changed.</span></span> <span data-ttu-id="34654-193">Per ottenere il file di immagine aggiornato, il client esegue di nuovo una query sul servizio ABWQ per aggiornare il file di immagine nella cache del client con il file di immagine nel server, che reimposta anche il **timestamp** nel file nella cache del client.</span><span class="sxs-lookup"><span data-stu-id="34654-193">To obtain the updated image file, the client again queries the ABWQ service to update the image file in the client cache with the image file on the server, which also resets the **TimeStamp** on the file in the client cache.</span></span>

<span data-ttu-id="34654-194">Di seguito è riportato un esempio di risposta a una query al servizio ABWQ:</span><span class="sxs-lookup"><span data-stu-id="34654-194">The following is an example response to a query to the ABWQ service:</span></span>
```xml
    <Attribute>
              <Name>PhotoRelPath</Name>
              <Value>efa6096aed2746cb9ab2037f7dbdde9d.f2eeeb5946db54a7aa607ecd3ae09d
              95.photo</Value>
              <Values xmlns:d6p1="http://schemas.microsoft.com/2003/10/Serialization/Arrays" i:nil="true" />
    </Attribute>
    <Attribute>
              <Name>PhotoHash</Name>
              <Value>f2eeeb5946db54a7aa607ecd3ae09d95</Value>
              <Values xmlns:d6p1="http://schemas.microsoft.com/2003/10/Serialization/Arrays" i:nil="true" />
    </Attribute>
    <Attribute>
         <Name>PhotoSize</Name>
         <Value>4620</Value>
         <Valuesxmlns:d6p1="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
    i:nil="true" />
    </Attribute>
```

</div>

</div>

<div>

## <a name="user-photos-in-lync-2013"></a><span data-ttu-id="34654-195">Foto degli utenti in Lync 2013</span><span class="sxs-lookup"><span data-stu-id="34654-195">User photos in Lync 2013</span></span>

<span data-ttu-id="34654-196">Lync 2013 ha introdotto il supporto per le immagini ad alta risoluzione per le foto degli utenti.</span><span class="sxs-lookup"><span data-stu-id="34654-196">Lync 2013 introduced support for high-resolution images for user photos.</span></span> <span data-ttu-id="34654-197">Lync 2013 include anche il supporto per l'archiviazione delle foto degli utenti nella cassetta postale dell'utente in Exchange 2013, che rimuove le limitazioni relative alla risoluzione e alle dimensioni delle immagini presenti in Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="34654-197">Lync 2013 also includes support for storing user photos in the user's mailbox on Exchange 2013, which removes the image resolution and size limitations present in Lync 2010.</span></span> <span data-ttu-id="34654-198">Le foto degli utenti in Lync 2013 possono contenere fino a 648 pixel per 648 pixel con una dimensione di file fino a 20 MB.</span><span class="sxs-lookup"><span data-stu-id="34654-198">User photos in Lync 2013 can be up to 648 pixels by 648 pixels with a file size of up to 20 MB.</span></span> <span data-ttu-id="34654-199">Le foto ad alta risoluzione in Lync 2013 devono trovarsi nella cassetta postale dell'utente in Exchange 2013 e sono supportate solo con il client Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="34654-199">High-resolution photos in Lync 2013 must be located in the user's mailbox on Exchange 2013, and are supported only with Lync 2013 client.</span></span> <span data-ttu-id="34654-200">Questa integrazione con Exchange sfrutta il nuovo Framework di autorizzazione incluso nelle versioni di 2013 di Lync, Exchange e SharePoint denominato OAuth.</span><span class="sxs-lookup"><span data-stu-id="34654-200">This integration with Exchange takes advantage of the new authorization framework included in the 2013 versions of Lync, Exchange, and SharePoint called Oauth.</span></span>

<span data-ttu-id="34654-201">Se Exchange 2013 non viene usato nella distribuzione, il supporto per le foto degli utenti è uguale a quello di Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="34654-201">If Exchange 2013 is not used in your deployment, support for user photos is the same as with Lync 2010.</span></span> <span data-ttu-id="34654-202">Tuttavia, le opzioni utente per scegliere la foto da usare sono diverse nel client Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="34654-202">However, the user options to choose the photo to use are different in Lync 2013 client.</span></span> <span data-ttu-id="34654-203">Nel client Lync 2013 gli utenti possono selezionare **Nascondi immagine** o **Mostra immagine personale**.</span><span class="sxs-lookup"><span data-stu-id="34654-203">In Lync 2013 client, users can select either **Hide my picture** or **Show my picture**.</span></span> <span data-ttu-id="34654-204">L'opzione **Mostra un'immagine da un sito Web** non è disponibile per impostazione predefinita, ma può essere abilitata assegnando un criterio client.</span><span class="sxs-lookup"><span data-stu-id="34654-204">The option **Show a picture from a website** is not available by default, but can be enabled by assigning a client policy.</span></span>

<div>

## <a name="hide-my-picture"></a><span data-ttu-id="34654-205">Nascondere l'immagine personale</span><span class="sxs-lookup"><span data-stu-id="34654-205">Hide my picture</span></span>

<span data-ttu-id="34654-206">Le impostazioni per le foto degli utenti si trovano nella finestra di dialogo **Opzioni** in Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="34654-206">Settings for user photos are on the **Options** dialog in Lync 2013.</span></span> <span data-ttu-id="34654-207">Quando si sceglie **Nascondi immagine personale**, non viene visualizzata alcuna foto utente nel client Lync, ma la foto viene ancora visualizzata nella scheda contatto e all'esterno di Lync.</span><span class="sxs-lookup"><span data-stu-id="34654-207">When you choose **Hide my picture**, no user photo is displayed for you in Lync client, but your photo is still displayed on your contact card and outside of Lync.</span></span>

</div>

<div>

## <a name="show-my-picture"></a><span data-ttu-id="34654-208">Mostrare l'immagine personale</span><span class="sxs-lookup"><span data-stu-id="34654-208">Show my picture</span></span>

<span data-ttu-id="34654-209">Quando si sceglie l'opzione **Mostra immagine personale** , la foto utente viene visualizzata nel client Lync e ad altri utenti nelle conversazioni di Lync.</span><span class="sxs-lookup"><span data-stu-id="34654-209">When you choose the **Show my picture** option, your user photo is displayed in your Lync client and to other users in Lync conversations.</span></span> <span data-ttu-id="34654-210">L'immagine usata è quella archiviata in servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="34654-210">The image used is the one stored in AD DS.</span></span>

</div>

<div>

## <a name="show-a-picture-from-a-website"></a><span data-ttu-id="34654-211">Visualizzare un'immagine da un sito Web</span><span class="sxs-lookup"><span data-stu-id="34654-211">Show a picture from a website</span></span>

<span data-ttu-id="34654-212">L'opzione **Mostra immagine da un sito Web** diventa disponibile in Lync 2013 dopo che è stato impostato un criterio client per abilitarlo.</span><span class="sxs-lookup"><span data-stu-id="34654-212">The **Show picture from a website** option becomes available in Lync 2013 after a client policy is set to enable it.</span></span> <span data-ttu-id="34654-213">La versione client deve essere più recente di 15.0.4535.1002, che viene installata con gli [aggiornamenti cumulativi di Lync: 2013 novembre](http://go.microsoft.com/fwlink/p/?linkid=509908).</span><span class="sxs-lookup"><span data-stu-id="34654-213">The client version must be newer than 15.0.4535.1002, which is installed with the [Lync Cumulative Updates: November 2013](http://go.microsoft.com/fwlink/p/?linkid=509908).</span></span> <span data-ttu-id="34654-214">Per visualizzare le modifiche apportate al client, è possibile che gli utenti debbano disconnettersi e quindi eseguire di nuovo il backup.</span><span class="sxs-lookup"><span data-stu-id="34654-214">Users may need to log out and then back in again to see the changes in the client.</span></span>

<span data-ttu-id="34654-215">Puoi impostare i criteri client per consentire di **visualizzare l'immagine da un'impostazione del sito Web** eseguendo il criterio [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) in Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="34654-215">You can set the client policy to enable to **Show picture from a website** setting by running the [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) policy in the Lync Server Management Shell.</span></span> <span data-ttu-id="34654-216">I cmdlet di esempio seguenti illustrano come impostare i criteri globalmente per tutti gli utenti della distribuzione:</span><span class="sxs-lookup"><span data-stu-id="34654-216">The following example cmdlets demonstrate how to set the policy globally for all users in your deployment:</span></span>

   ```powershell
    $pe=New-CsClientPolicyEntry -Name EnablePresencePhotoOptions -Value True
   ```

   ```powershell
    $po=Get-CsClientPolicy -Identity Global
   ```

   ```powershell
    $po.PolicyEntry.Add($pe)
   ```

   ```powershell
    Set-CsClientPolicy -Instance $po
   ```


<span data-ttu-id="34654-217">Quando un'immagine viene caricata nella cassetta postale dell'utente, Exchange crea automaticamente una versione di risoluzione inferiore dell'immagine che può essere usata nelle applicazioni client.</span><span class="sxs-lookup"><span data-stu-id="34654-217">When an image is uploaded to the user’s mailbox, Exchange automatically creates a lower resolution version of the image which can be used in client applications.</span></span> <span data-ttu-id="34654-218">La foto utente viene aggiornata anche in servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="34654-218">The user photo is also updated in AD DS.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="34654-219">Quando un file di immagine viene aggiornato in servizi di dominio Active Directory, viene creata e usata un'immagine pixel di 48 x 48 per thumbnailPhoto in servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="34654-219">When an image file is updated in AD DS, a 48 x 48 pixel image is created and used for the thumbnailPhoto in AD DS.</span></span> <span data-ttu-id="34654-220">Qualsiasi immagine esistente viene sostituita.</span><span class="sxs-lookup"><span data-stu-id="34654-220">Any existing image is replaced.</span></span> <span data-ttu-id="34654-221">Quindi, se è stata aggiunta un'immagine di 96 x 96 a servizi di dominio Active Directory, verrà sovrascritta con la nuova immagine di 48 x 48.</span><span class="sxs-lookup"><span data-stu-id="34654-221">So if you added a 96 x 96 image to AD DS, it will be overwritten with the new 48 x 48 image.</span></span> <span data-ttu-id="34654-222">Questa operazione è importante solo per gli utenti dell'ambiente che usano i client Lync 2010, in quanto tali client otterranno le foto degli utenti da servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="34654-222">This is only important is you have users in your environment using Lync 2010 clients, as those clients will obtain user photos from AD DS.</span></span> <span data-ttu-id="34654-223">È possibile importare immagini in pixel di 96 x 96 in sostituzione di quelle create da servizi di dominio Active Directory se sono presenti client Lync 2010 nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="34654-223">You can import 96 x 96 pixel images to replace the ones created by AD DS if you have Lync 2010 clients in your organization.</span></span>



</div>

</div>

<div>

## <a name="user-photo-support-in-lync-2013"></a><span data-ttu-id="34654-224">Supporto per le foto degli utenti in Lync 2013</span><span class="sxs-lookup"><span data-stu-id="34654-224">User photo support in Lync 2013</span></span>

<span data-ttu-id="34654-225">In Lync 2013 sono supportate tre risoluzioni di immagine per le foto degli utenti, come descritto nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="34654-225">In Lync 2013, three image resolutions are supported for user photos as described in the following table.</span></span> <span data-ttu-id="34654-226">L'immagine usata è determinata dall'impostazione del criterio client assegnata agli utenti di Lync.</span><span class="sxs-lookup"><span data-stu-id="34654-226">The image that is used is determined by the client policy setting assigned to Lync users.</span></span> <span data-ttu-id="34654-227">Per altre informazioni, vedere "gestione della foto dell'utente con i cmdlet dei criteri client" in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="34654-227">See “Managing user’s photo with Client Policy cmdlets” in this topic for more information.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="34654-228">Risoluzione immagine (pixel)</span><span class="sxs-lookup"><span data-stu-id="34654-228">Image resolution (pixels)</span></span></th>
<th><span data-ttu-id="34654-229">Applicazione</span><span class="sxs-lookup"><span data-stu-id="34654-229">Application</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="34654-230">48 x 48</span><span class="sxs-lookup"><span data-stu-id="34654-230">48 x 48</span></span></p></td>
<td><p><span data-ttu-id="34654-231">Usato se non è selezionata un'immagine con risoluzione superiore</span><span class="sxs-lookup"><span data-stu-id="34654-231">Used if no higher resolution image is selected</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34654-232">96 x 96</span><span class="sxs-lookup"><span data-stu-id="34654-232">96 x 96</span></span></p></td>
<td><p><span data-ttu-id="34654-233">Usato in Outlook Web App e Outlook 2013</span><span class="sxs-lookup"><span data-stu-id="34654-233">Used in Outlook Web App and Outlook 2013</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34654-234">648 x 648</span><span class="sxs-lookup"><span data-stu-id="34654-234">648 x 648</span></span></p></td>
<td><p><span data-ttu-id="34654-235">Usato nel client desktop Lync 2013 e in Lync 2013 Web App</span><span class="sxs-lookup"><span data-stu-id="34654-235">Used in Lync 2013 desktop client and Lync 2013 Web App</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="34654-236">Qualsiasi utente con una cassetta postale abilitata in Exchange 2013 può caricare un'immagine diversa, incluse le foto ad alta risoluzione, tramite Outlook Web Access o le opzioni client di Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="34654-236">Any user with a mailbox enabled in Exchange 2013 can upload a different image, including high-resolution photos, through Outlook Web Access or Lync 2013 client options.</span></span> <span data-ttu-id="34654-237">Le impostazioni consigliate per le immagini usate includono:</span><span class="sxs-lookup"><span data-stu-id="34654-237">The recommended settings for images used include:</span></span>

  - <span data-ttu-id="34654-238">**Risoluzione immagine 648**   per 648 pixel</span><span class="sxs-lookup"><span data-stu-id="34654-238">**Image Resolution**   648 by 648 pixels</span></span>

  - <span data-ttu-id="34654-239">**Profondità di colore**   a 24 bit</span><span class="sxs-lookup"><span data-stu-id="34654-239">**Color Depth**   24-bit</span></span>

  - <span data-ttu-id="34654-240">**Dimensioni del file di immagine**   fino a 20 MB</span><span class="sxs-lookup"><span data-stu-id="34654-240">**Image file size**   up to 20 MB</span></span>

  - <span data-ttu-id="34654-241">**Formato file JPEG**   </span><span class="sxs-lookup"><span data-stu-id="34654-241">**File format**   JPEG</span></span>

<span data-ttu-id="34654-242">Un'immagine JPEG a 24 bit tipica di 648 pixel per 648 pixel ha una dimensione di file di circa 240 KB, quindi è necessario 1 MB di spazio di archiviazione per ogni 4 foto utente.</span><span class="sxs-lookup"><span data-stu-id="34654-242">A typical 24-bit JPEG image that is 648 pixels by 648 pixels has a file size of about 240 KB, so 1 MB of storage space is needed for every 4 user photos.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

