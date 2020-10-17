---
title: Modalità di visualizzazione delle foto degli utenti in Lync
description: Modalità di visualizzazione delle foto degli utenti in Lync.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: How user photos are displayed in Lync
ms:assetid: b44a364d-a1d2-4d45-b27a-b5f77775e233
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn783119(v=OCS.15)
ms:contentKeyID: 62835297
ms.date: 08/27/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 12ea9e19b3965994c025659f1b2249c49ec32a3a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551112"
---
# <a name="how-user-photos-are-displayed-in-lync"></a><span data-ttu-id="55511-103">Modalità di visualizzazione delle foto degli utenti in Lync</span><span class="sxs-lookup"><span data-stu-id="55511-103">How user photos are displayed in Lync</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="55511-104">_**Ultimo argomento modificato:** 2014-08-25_</span><span class="sxs-lookup"><span data-stu-id="55511-104">_**Topic Last Modified:** 2014-08-25_</span></span>

<span data-ttu-id="55511-105">**Riepilogo:** Le foto degli utenti visualizzate nel client Lync possono variare a seconda della caratteristica di Lync in uso, ad esempio in una conferenza o in una chat di messaggistica istantanea.</span><span class="sxs-lookup"><span data-stu-id="55511-105">**Summary:** User photos displayed in Lync client can be different depending on which Lync feature you are using, such as when in a conference or an IM chat.</span></span>

<span data-ttu-id="55511-106">Lync 2010 è stata introdotta la possibilità di includere una foto con il profilo di Lync visualizzato ad altri utenti di Lync.</span><span class="sxs-lookup"><span data-stu-id="55511-106">Lync 2010 introduced the ability to include a photo with your Lync profile that is displayed to other Lync users.</span></span> <span data-ttu-id="55511-107">È anche possibile scegliere se visualizzare o meno le foto per i contatti nel client Lync.</span><span class="sxs-lookup"><span data-stu-id="55511-107">You can also choose whether or not to display photos for your contacts in Lync client.</span></span> <span data-ttu-id="55511-108">In Lync 2013, supporto per le foto ad alta risoluzione per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="55511-108">In Lync 2013, support for high-resolution photos for users.</span></span> <span data-ttu-id="55511-109">In questo argomento viene descritto il modo in cui il client Lync ottiene e visualizza le foto degli utenti, in cui vengono archiviate le immagini, le limitazioni per ogni origine di immagine e la modalità di utilizzo delle foto degli utenti da diversi servizi Lync.</span><span class="sxs-lookup"><span data-stu-id="55511-109">This topic describes how Lync client gets and displays user photos, where the images are stored, the limitations for each image source, and how user photos are used by different Lync services.</span></span>

<div>

## <a name="planning-considerations"></a><span data-ttu-id="55511-110">Considerazioni sulla pianificazione</span><span class="sxs-lookup"><span data-stu-id="55511-110">Planning considerations</span></span>

<span data-ttu-id="55511-111">Quando si pianifica l'implementazione del supporto per le foto degli utenti, è necessario tenere presente quanto segue.</span><span class="sxs-lookup"><span data-stu-id="55511-111">You should consider the following when planning to implement support for user photos.</span></span>

  - <span data-ttu-id="55511-112">Il supporto per le foto degli utenti ad alta definizione richiede che la cassetta postale dell'utente sia presente in Exchange 2013 e che l'account utente di Lync sia incluso nel pool Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="55511-112">High-definition user photo support requires that the user’s mailbox be located on Exchange 2013 and the Lync user account to be in Lync 2013 pool.</span></span>

  - <span data-ttu-id="55511-113">Le foto degli utenti ad alta definizione sono supportate solo in un ambiente in cui vengono utilizzati sia Lync Server 2013 che Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="55511-113">High-definition user photos are supported only in an environment where both Lync Server 2013 and Exchange 2013 are used.</span></span>

  - <span data-ttu-id="55511-114">Gli utenti con cassette postali su Exchange 2010 utilizzeranno sempre l'attributo **ThumbNailPhoto** di ad DS come origine per la foto dell'utente.</span><span class="sxs-lookup"><span data-stu-id="55511-114">Users with Mailboxes on Exchange 2010 will always use the **thumbnailPhoto** attribute from AD DS as the source for their user photo.</span></span>

  - <span data-ttu-id="55511-115">Una foto utente memorizzata come attributo **ThumbNailPhoto** da servizi di dominio Active Directory non verrà visualizzata per i contatti esterni/federati.</span><span class="sxs-lookup"><span data-stu-id="55511-115">A user photo stored as the **thumbnailPhoto** attribute from AD DS will not be displayed to external / federated contacts.</span></span>

  - <span data-ttu-id="55511-116">Se le foto dei contatti utente sono archiviate in servizi di dominio Active Directory, il file di immagine utilizzato è limitato a 96 × 96 pixel e non supera le dimensioni del file di 100 KB.</span><span class="sxs-lookup"><span data-stu-id="55511-116">If the photos for user contacts are stored in AD DS, the image file used is limited to 96×96 pixels and no more than 100 KB file size.</span></span>

  - <span data-ttu-id="55511-117">Se la connettività tra Lync Server e Exchange Server viene persa, l' **ThumbNailPhoto** a bassa risoluzione dell'utente da servizi di dominio Active Directory verrà visualizzato e solo per gli utenti interni.</span><span class="sxs-lookup"><span data-stu-id="55511-117">If connectivity between Lync Server and Exchange Server is lost, the user’s low resolution **thumbnailPhoto** from AD DS will be displayed, and to internal users only.</span></span>

  - <span data-ttu-id="55511-118">Le foto degli utenti ad alta risoluzione vengono visualizzate nelle riunioni di Lync 2013 quando un altoparlante attivo non dispone di video abilitato.</span><span class="sxs-lookup"><span data-stu-id="55511-118">High-resolution user photos are displayed in Lync 2013 meetings when an active speaker does not have video enabled.</span></span> <span data-ttu-id="55511-119">Inoltre, se si sposta il puntatore del mouse sulla foto di anteprima nella raccolta, viene visualizzata la foto ad alta risoluzione.</span><span class="sxs-lookup"><span data-stu-id="55511-119">Also, moving the mouse over thumbnail photo in the gallery will display the high-resolution photo.</span></span>

</div>

<div>

## <a name="user-photos-in-lync-2010"></a><span data-ttu-id="55511-120">Foto degli utenti in Lync 2010</span><span class="sxs-lookup"><span data-stu-id="55511-120">User Photos in Lync 2010</span></span>

<span data-ttu-id="55511-121">Nel client Lync 2010, è possibile scegliere tra due opzioni per visualizzare una foto per il profilo, l' **immagine aziendale predefinita** e la visualizzazione **dell'immagine da un indirizzo Web**.</span><span class="sxs-lookup"><span data-stu-id="55511-121">In the Lync 2010 client, you can choose from two options to display a photo for your profile, **Default corporate picture** and **Show picture from a web address**.</span></span>

<div>

## <a name="default-corporate-picture"></a><span data-ttu-id="55511-122">Immagine aziendale predefinita</span><span class="sxs-lookup"><span data-stu-id="55511-122">Default corporate picture</span></span>

<span data-ttu-id="55511-123">Quando si sceglie l'opzione **immagine aziendale predefinita** , Lync ottiene la foto visualizzata per l'utente da servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="55511-123">When you choose the **Default corporate picture** option, Lync gets the photo displayed for you from Active Directory Domain Services.</span></span> <span data-ttu-id="55511-124">L'immagine utilizzata è l'immagine definita come valore per l'attributo **ThumbNailPhoto** in servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="55511-124">The image used is the image defined as the value for the **thumbnailPhoto** attribute in Active Directory Domain Services.</span></span> <span data-ttu-id="55511-125">Questo è lo stesso file utilizzato da Exchange per visualizzare le immagini in Outlook.</span><span class="sxs-lookup"><span data-stu-id="55511-125">This is the same file that is used by Exchange to display images in Outlook.</span></span>

<span data-ttu-id="55511-126">Di seguito sono riportate le considerazioni relative all'utilizzo di immagini da servizi di dominio Active Directory:</span><span class="sxs-lookup"><span data-stu-id="55511-126">Considerations for using images from Active Directory Domain Services include the following:</span></span>

  - <span data-ttu-id="55511-127">Sono supportate solo le immagini con dimensioni fino a 96 pixel per 96 pixel.</span><span class="sxs-lookup"><span data-stu-id="55511-127">Only images with dimensions up to 96 pixels by 96 pixels are supported.</span></span> <span data-ttu-id="55511-128">Le dimensioni dei file per l'immagine sono limitate a 100 KB.</span><span class="sxs-lookup"><span data-stu-id="55511-128">The file size for the image is limited to 100 KB.</span></span>

  - <span data-ttu-id="55511-129">Per impostazione predefinita, gli utenti sono in grado di modificare l'immagine utilizzata per l'attributo **ThumbNailPhoto** , anche se non direttamente tramite il client Lync.</span><span class="sxs-lookup"><span data-stu-id="55511-129">By default, users are able to change the image used for the **thumbnailPhoto** attribute, though not directly through Lync client.</span></span> <span data-ttu-id="55511-130">È possibile disabilitarlo tramite servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="55511-130">You can disable this through Active Directory Domain Services.</span></span>

  - <span data-ttu-id="55511-131">Le immagini archiviate in servizi di dominio Active Directory non vengono visualizzate ai contatti esterni all'organizzazione, anche se sono contatti federati.</span><span class="sxs-lookup"><span data-stu-id="55511-131">Images stored in Active Directory Domain Services are not displayed to contacts external to your organization, even if they are federated contacts.</span></span>

  - <span data-ttu-id="55511-132">Nelle organizzazioni di grandi dimensioni, l'archiviazione e il recupero delle immagini per un numero elevato di utenti possono influire sulle prestazioni e le dimensioni del database di servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="55511-132">In large organizations, storing and retrieving the images for large numbers of users may impact the Active Directory Domain Services database size and performance.</span></span>

  - <span data-ttu-id="55511-133">Le dimensioni limitate delle immagini e le dimensioni dei file indicano che è possibile utilizzare solo immagini a bassa risoluzione.</span><span class="sxs-lookup"><span data-stu-id="55511-133">The limited image dimensions and file size mean that only low resolution images can be used.</span></span>

<div>

## <a name="how-users-manage-their-user-photos-in-active-directory-domain-services"></a><span data-ttu-id="55511-134">Come gli utenti gestiscono le proprie foto utente in servizi di dominio Active Directory</span><span class="sxs-lookup"><span data-stu-id="55511-134">How users manage their user photos in Active Directory Domain Services</span></span>

<span data-ttu-id="55511-135">L'utente non può modificare l'immagine utilizzata nel proprio profilo servizi di dominio Active Directory direttamente tramite il client Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="55511-135">User cannot change the image used in their Active Directory Domain Services profile directly through Lync 2010 client.</span></span> <span data-ttu-id="55511-136">Se disponibile, è possibile utilizzare una delle seguenti opzioni:</span><span class="sxs-lookup"><span data-stu-id="55511-136">They can use one of the following options to do so, if available:</span></span>

  - <span data-ttu-id="55511-137">**SharePoint Server**     Gli utenti possono caricare una foto in "sito personale" in un server di SharePoint e quindi [configurare la sincronizzazione dei profili in SharePoint](https://go.microsoft.com/fwlink/p/?linkid=507466) per sincronizzare la foto con l'attributo **ThumbNailPhoto** in servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="55511-137">**SharePoint Server**   Users can upload a photo to ‘My Site’ on a SharePoint Server and then [configure profile synchronization in SharePoint](https://go.microsoft.com/fwlink/p/?linkid=507466) to synchronize the photo to the **thumbnailPhoto** attribute in Active Directory Domain Services.</span></span>

  - <span data-ttu-id="55511-138">**Foto memorizzata in un URL**     accessibile pubblicamente Gli utenti possono configurare la foto utente specificando un URL accessibile pubblicamente per l'immagine che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="55511-138">**Photo stored on publicly accessible URL**   Users can configure their user photo specifying a publicly accessible URL for the image that they want to use.</span></span> <span data-ttu-id="55511-139">L'immagine deve essere accessibile pubblicamente senza una password.</span><span class="sxs-lookup"><span data-stu-id="55511-139">The image must be publicly accessible without a password.</span></span> <span data-ttu-id="55511-140">L'immagine memorizzata nell'indirizzo Web specificato viene trasferita ad altri utenti tramite la categoria di schede contatto nelle informazioni sulla presenza.</span><span class="sxs-lookup"><span data-stu-id="55511-140">The image stored at the specified web address is transferred to other users through the contact card category in the presence information.</span></span> <span data-ttu-id="55511-141">Quando il client Lync deve visualizzare una foto utente, l'immagine viene recuperata dall'indirizzo Web specificato.</span><span class="sxs-lookup"><span data-stu-id="55511-141">When Lync client needs to display a user photo, it retrieves the image from the specified web address.</span></span>

  - <span data-ttu-id="55511-142">**Cmdlet di Exchange 2010 per Windows PowerShell**     Gli amministratori possono eseguire il cmdlet [Import-RecipientDataProperty](https://go.microsoft.com/fwlink/p/?linkid=507468) in Exchange 2010 Management Shell in per gestire l'attributo **ThumbNailPhoto** .</span><span class="sxs-lookup"><span data-stu-id="55511-142">**Exchange 2010 cmdlets for Windows PowerShell**   Administrators can run the [Import-RecipientDataProperty](https://go.microsoft.com/fwlink/p/?linkid=507468) cmdlet in the Exchange 2010 Management Shell in to manage the **thumbnailPhoto** attribute.</span></span> <span data-ttu-id="55511-143">Quando le immagini vengono importate con i cmdlet di Exchange 2010, la dimensione del file è limitata a 10 KB.</span><span class="sxs-lookup"><span data-stu-id="55511-143">When images are imported with Exchange 2010 cmdlets, the file size is limited to 10 KB.</span></span>

  - <span data-ttu-id="55511-144">Strumenti di terze **parti**     Gli utenti possono caricare solo la propria foto per l'attributo **ThumbNailPhoto** .</span><span class="sxs-lookup"><span data-stu-id="55511-144">**Third Party tools**   Users can upload only their own photo to for the **thumbnailPhoto** attribute.</span></span>

</div>

</div>

<div>

## <a name="show-a-picture-from-a-web-address"></a><span data-ttu-id="55511-145">Mostra l'immagine da un indirizzo Web</span><span class="sxs-lookup"><span data-stu-id="55511-145">Show a picture from a web address</span></span>

<span data-ttu-id="55511-146">Quando si sceglie l'opzione **Mostra un'immagine da un indirizzo Web** , Lync ottiene l'immagine all'indirizzo immesso e la Visualizza per la foto dell'utente in Lync.</span><span class="sxs-lookup"><span data-stu-id="55511-146">When you choose the **Show a picture from a web address** option, Lync gets the image at the address you enter and displays it for your user photo in Lync.</span></span>

<span data-ttu-id="55511-147">Di seguito sono riportate le considerazioni relative all'utilizzo di immagini da un indirizzo Web:</span><span class="sxs-lookup"><span data-stu-id="55511-147">Considerations for using images from a web address include the following:</span></span>

  - <span data-ttu-id="55511-148">I limiti relativi alle dimensioni dei file sono determinati dall'attributo **MaxPhotoSizeKB** nel criterio client, definito con il cmdlet [New-CsClientPolicy](https://go.microsoft.com/fwlink/p/?linkid=507463) .</span><span class="sxs-lookup"><span data-stu-id="55511-148">File size limits are determined by the **MaxPhotoSizeKB** attribute in the client policy, defined with the [New-CsClientPolicy](https://go.microsoft.com/fwlink/p/?linkid=507463) cmdlet.</span></span> <span data-ttu-id="55511-149">Il limite di dimensione predefinito è 30 KB.</span><span class="sxs-lookup"><span data-stu-id="55511-149">The default size limit is 30 KB.</span></span> <span data-ttu-id="55511-150">Il valore massimo è 100 KB.</span><span class="sxs-lookup"><span data-stu-id="55511-150">The maximum value is 100 KB.</span></span> <span data-ttu-id="55511-151">Non vi sono restrizioni sulla risoluzione dell'immagine, ma se si tenta di utilizzare un file di immagine che supera il limite di dimensione, non verrà scaricato nei client Lync.</span><span class="sxs-lookup"><span data-stu-id="55511-151">There is no restriction on the resolution of the image, but if you try to use an image file that exceeds the size limit it will not be downloaded to Lync clients.</span></span> <span data-ttu-id="55511-152">È possibile impostare il valore su 0 per disabilitare l'utilizzo di tutte le foto degli utenti in Lync.</span><span class="sxs-lookup"><span data-stu-id="55511-152">You can set the value to 0 to disable all user photos from being used in Lync.</span></span>

  - <span data-ttu-id="55511-153">Le foto degli utenti provenienti da un indirizzo Web possono essere visualizzate da contatti federati esterni.</span><span class="sxs-lookup"><span data-stu-id="55511-153">User photos from a web address can be seen by external federated contacts.</span></span>

</div>

<div>

## <a name="managing-users-photo-with-client-policy-cmdlets"></a><span data-ttu-id="55511-154">Gestione delle foto degli utenti con i cmdlet dei criteri client</span><span class="sxs-lookup"><span data-stu-id="55511-154">Managing user’s photo with Client Policy cmdlets</span></span>

<span data-ttu-id="55511-155">In Lync Server 2010, le impostazioni dei criteri client sono configurate con i cmdlet di CsClientPolicy.</span><span class="sxs-lookup"><span data-stu-id="55511-155">In Lync Server 2010, client policy settings are configured with the CsClientPolicy cmdlets.</span></span> <span data-ttu-id="55511-156">Le impostazioni dei criteri configurate vengono inviate ai client tramite il provisioning in-band.</span><span class="sxs-lookup"><span data-stu-id="55511-156">The configured policy settings are sent to clients through in-band provisioning.</span></span> <span data-ttu-id="55511-157">I due parametri dei cmdlet di CsClientPolicy che determinano l'esperienza della foto utente sono **DisplayPhoto** e **MaxPhotoSizeKB**.</span><span class="sxs-lookup"><span data-stu-id="55511-157">The two parameters of the CsClientPolicy cmdlets that determine the user photo experience are **DisplayPhoto** and **MaxPhotoSizeKB**.</span></span> <span data-ttu-id="55511-158">Il parametro di provisioning di tipo in-band corrispondente per **DisplayPhoto** e **MaxPhotoSizeKB** è denominato **fotoutilizzo**.</span><span class="sxs-lookup"><span data-stu-id="55511-158">The corresponding in-band provisioning parameter for **DisplayPhoto** and **MaxPhotoSizeKB** is named **PhotoUsage**.</span></span> <span data-ttu-id="55511-159">I valori per il parametro **DataUsage** sono Send to clients through the **EndpointConfiguration** **provisionGroup**.</span><span class="sxs-lookup"><span data-stu-id="55511-159">Values for the **PhotoUsage** parameter are send to clients through the **endpointConfiguration** **provisionGroup**.</span></span> <span data-ttu-id="55511-160">Per ulteriori informazioni, vedere [Overview of client Policies and Settings](https://go.microsoft.com/fwlink/?linkid=507470) .</span><span class="sxs-lookup"><span data-stu-id="55511-160">See [Overview of Client Policies and Settings](https://go.microsoft.com/fwlink/?linkid=507470) for more information.</span></span>

<span data-ttu-id="55511-161">Il valore del parametro **DisplayPhoto** determina l'origine dell'immagine della foto dell'utente.</span><span class="sxs-lookup"><span data-stu-id="55511-161">The **DisplayPhoto** parameter value determines the source of the user's photo image.</span></span> <span data-ttu-id="55511-162">I valori supportati sono inclusi nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="55511-162">The supported values are included in the following table.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="55511-163">Valore del parametro DisplayPhoto</span><span class="sxs-lookup"><span data-stu-id="55511-163">DisplayPhoto parameter value</span></span></th>
<th><span data-ttu-id="55511-164">Origine immagine</span><span class="sxs-lookup"><span data-stu-id="55511-164">Image source</span></span></th>
<th><span data-ttu-id="55511-165">Impostazioni client di Lync 2010</span><span class="sxs-lookup"><span data-stu-id="55511-165">Lync 2010 client settings</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="55511-166">Nophoto</span><span class="sxs-lookup"><span data-stu-id="55511-166">NoPhoto</span></span></p></td>
<td><p><span data-ttu-id="55511-167">nessuno</span><span class="sxs-lookup"><span data-stu-id="55511-167">none</span></span></p></td>
<td><p><span data-ttu-id="55511-168"><strong>Non mostrare l'immagine personale</strong></span><span class="sxs-lookup"><span data-stu-id="55511-168"><strong>Do not show my picture</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55511-169">PhotoFromADOnly</span><span class="sxs-lookup"><span data-stu-id="55511-169">PhotoFromADOnly</span></span></p></td>
<td><p><span data-ttu-id="55511-170">Active Directory</span><span class="sxs-lookup"><span data-stu-id="55511-170">Active Directory</span></span></p></td>
<td><p><span data-ttu-id="55511-171"><strong>Immagine aziendale predefinita</strong></span><span class="sxs-lookup"><span data-stu-id="55511-171"><strong>Default corporate picture</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="55511-172">AllPhotos</span><span class="sxs-lookup"><span data-stu-id="55511-172">AllPhotos</span></span></p></td>
<td><p><span data-ttu-id="55511-173">Indirizzo Web</span><span class="sxs-lookup"><span data-stu-id="55511-173">Web address</span></span></p></td>
<td><p><span data-ttu-id="55511-174"><strong>Mostra l'immagine da un indirizzo Web</strong></span><span class="sxs-lookup"><span data-stu-id="55511-174"><strong>Show a picture from a web address</strong></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="how-lync-2010-client-gets-photos"></a><span data-ttu-id="55511-175">Come viene ottenuta la foto dal client Lync 2010</span><span class="sxs-lookup"><span data-stu-id="55511-175">How Lync 2010 client gets photos</span></span>

<span data-ttu-id="55511-176">In Lync 2010, le foto degli utenti vengono gestite sul server dal servizio Rubrica.</span><span class="sxs-lookup"><span data-stu-id="55511-176">In Lync 2010, user photos are managed on the server by the Address Book Service.</span></span> <span data-ttu-id="55511-177">Il client Lync ottiene le foto degli utenti eseguendo prima una query sul servizio query Web della Rubrica (ABWQ) nel server, esposto tramite il servizio Web di espansione della lista di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="55511-177">Lync client gets user photos by first querying the Address Book Web Query (ABWQ) service on the server, which is exposed through the Distribution List Expansion web service.</span></span> <span data-ttu-id="55511-178">Il client riceve il file di immagine e quindi lo copia nella cache dell'utente per evitare di scaricare l'immagine ogni volta che deve essere visualizzata.</span><span class="sxs-lookup"><span data-stu-id="55511-178">The client receives the image file and then copies it to the user's cache to avoid downloading the image each time it needs to be displayed.</span></span> <span data-ttu-id="55511-179">I valori degli attributi restituiti dalla query vengono archiviati anche nella voce del servizio rubrica memorizzata nella cache per l'utente.</span><span class="sxs-lookup"><span data-stu-id="55511-179">The attribute values returned from the query are also stored in the cached Address Book Service entry for the user.</span></span> <span data-ttu-id="55511-180">Il servizio Rubrica Elimina tutte le immagini memorizzate nella cache ogni 24 ore, il che significa che possono essere necessarie fino a 24 ore prima che le nuove immagini degli utenti vengano aggiornate nella cache sul server.</span><span class="sxs-lookup"><span data-stu-id="55511-180">The Address Book Service deletes all cached images every 24 hours, which means that it can take up to 24 hours for new user images to be updated in the cache on the server.</span></span> <span data-ttu-id="55511-181">È possibile forzare un aggiornamento alla cache utilizzando il cmdlet [Update-CsAddressBook](https://docs.microsoft.com/powershell/module/skype/Update-CsAddressBook) .</span><span class="sxs-lookup"><span data-stu-id="55511-181">You can force an update to the cache by using the [Update-CsAddressBook](https://docs.microsoft.com/powershell/module/skype/Update-CsAddressBook) cmdlet.</span></span>

<span data-ttu-id="55511-182">Le foto degli utenti incluse nello stato di presenza dispongono anche di un valore hash associato utilizzato dal client Lync per determinare se è disponibile un'immagine più recente.</span><span class="sxs-lookup"><span data-stu-id="55511-182">User photos included in Presence status also have an associated hash value that Lync client uses to determine whether there is a newer image available.</span></span> <span data-ttu-id="55511-183">Il client riceve automaticamente una notifica delle modifiche apportate al file di immagine utilizzato nello stato di presenza.</span><span class="sxs-lookup"><span data-stu-id="55511-183">The client is automatically notified of changes to the image file used in Presence status.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="55511-184">Poiché le foto non sono archiviate nel database di GalContacts. DB, il download delle foto utente non dipende dall'impostazione <STRONG>AddressBookAvailability</STRONG> nel criterio client (<A href="https://go.microsoft.com/fwlink/p/?linkid=507508">Set-CsClientPolicy</A>).</span><span class="sxs-lookup"><span data-stu-id="55511-184">Because photos are not stored in the GalContacts.db database, downloading user photos is not dependent on the <STRONG>AddressBookAvailability</STRONG> setting in the client policy (<A href="https://go.microsoft.com/fwlink/p/?linkid=507508">Set-CsClientPolicy</A>).</span></span>



</div>

<span data-ttu-id="55511-185">La query per il servizio ABWQ include gli attributi seguenti:</span><span class="sxs-lookup"><span data-stu-id="55511-185">The query to the ABWQ service includes the following attributes:</span></span>

  - <span data-ttu-id="55511-186">**Fotohash**     Il valore hash dei dati delle foto binarie viene utilizzato per determinare se la foto corrente è stata modificata.</span><span class="sxs-lookup"><span data-stu-id="55511-186">**PhotoHash**   The hash value of the binary photo data, and is used to determine whether the current photo has changed.</span></span>

  - <span data-ttu-id="55511-187">**PhotoRelPath**     Percorso relativo del file di immagine memorizzato nel server.</span><span class="sxs-lookup"><span data-stu-id="55511-187">**PhotoRelPath**   The relative path to the image file stored on the server.</span></span>

  - <span data-ttu-id="55511-188">**Fotosize**     Le dimensioni del file di immagine, in byte.</span><span class="sxs-lookup"><span data-stu-id="55511-188">**PhotoSize**   The size of the image file, in bytes.</span></span>

  - <span data-ttu-id="55511-189">**Timestamp**     La data e l'ora in cui è stato scaricato l'ultimo file di immagine dal server e copiati nella cache client.</span><span class="sxs-lookup"><span data-stu-id="55511-189">**TimeStamp**   The date and time at which the image file was last downloaded from the server and copied to the client cache.</span></span>

<span data-ttu-id="55511-190">Successivamente, dopo aver recuperato il file di immagine, Lync 2010 client confronta i valori degli attributi restituiti dalla query in base ai valori di attributo ricevuti dal client dal provisioning di tipo in-band per verificare se sono diversi.</span><span class="sxs-lookup"><span data-stu-id="55511-190">Next, after retrieving the image file, Lync 2010 client compares the attribute values returned from the query against the attribute values received by the client from in-band provisioning to see if they are different.</span></span> <span data-ttu-id="55511-191">Se i valori sono diversi, il client recupererà il file di immagine dell'utente connesso con una richiesta HTTP GET.</span><span class="sxs-lookup"><span data-stu-id="55511-191">If the values are different, the client retrieves the image file of the signed-in user with an HTTP GET request.</span></span>

<span data-ttu-id="55511-192">Inoltre, il client verifica con il server ogni 24 ore dal momento in cui è stata creata la versione memorizzata nella cache del file di immagine per confrontare il valore dell'attributo **fotohash** sul server con il valore sul client.</span><span class="sxs-lookup"><span data-stu-id="55511-192">Additionally, the client checks with the server every 24 hours from the time at which the cached version of the image file was created to compare the value of the **PhotoHash** attribute on the server with the value on the client.</span></span> <span data-ttu-id="55511-193">Se i valori sono diversi, il client sa che il file di immagine è stato modificato.</span><span class="sxs-lookup"><span data-stu-id="55511-193">If the values are different, the client knows that the image file has changed.</span></span> <span data-ttu-id="55511-194">Per ottenere il file di immagine aggiornato, il client esegue di nuovo una query sul servizio ABWQ per aggiornare il file di immagine nella cache del client con il file di immagine nel server, che reimposta anche il **timestamp** sul file nella cache client.</span><span class="sxs-lookup"><span data-stu-id="55511-194">To obtain the updated image file, the client again queries the ABWQ service to update the image file in the client cache with the image file on the server, which also resets the **TimeStamp** on the file in the client cache.</span></span>

<span data-ttu-id="55511-195">Di seguito è riportato un esempio di risposta a una query per il servizio ABWQ:</span><span class="sxs-lookup"><span data-stu-id="55511-195">The following is an example response to a query to the ABWQ service:</span></span>
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

## <a name="user-photos-in-lync-2013"></a><span data-ttu-id="55511-196">Foto degli utenti in Lync 2013</span><span class="sxs-lookup"><span data-stu-id="55511-196">User photos in Lync 2013</span></span>

<span data-ttu-id="55511-197">Lync 2013 ha introdotto il supporto per le immagini ad alta risoluzione per le foto degli utenti.</span><span class="sxs-lookup"><span data-stu-id="55511-197">Lync 2013 introduced support for high-resolution images for user photos.</span></span> <span data-ttu-id="55511-198">Lync 2013 include anche il supporto per l'archiviazione delle foto degli utenti nella cassetta postale dell'utente su Exchange 2013, che rimuove la risoluzione dell'immagine e le limitazioni relative alle dimensioni presenti in Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="55511-198">Lync 2013 also includes support for storing user photos in the user's mailbox on Exchange 2013, which removes the image resolution and size limitations present in Lync 2010.</span></span> <span data-ttu-id="55511-199">Le foto degli utenti in Lync 2013 possono essere fino a 648 pixel per 648 pixel con dimensioni di un file fino a 20 MB.</span><span class="sxs-lookup"><span data-stu-id="55511-199">User photos in Lync 2013 can be up to 648 pixels by 648 pixels with a file size of up to 20 MB.</span></span> <span data-ttu-id="55511-200">Le foto ad alta risoluzione in Lync 2013 devono essere situate nella cassetta postale dell'utente su Exchange 2013 e sono supportate solo con il client Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="55511-200">High-resolution photos in Lync 2013 must be located in the user's mailbox on Exchange 2013, and are supported only with Lync 2013 client.</span></span> <span data-ttu-id="55511-201">Questa integrazione con Exchange si avvale del nuovo Framework di autorizzazione incluso nelle versioni 2013 di Lync, Exchange e SharePoint denominato OAuth.</span><span class="sxs-lookup"><span data-stu-id="55511-201">This integration with Exchange takes advantage of the new authorization framework included in the 2013 versions of Lync, Exchange, and SharePoint called Oauth.</span></span>

<span data-ttu-id="55511-202">Se Exchange 2013 non viene utilizzato nella distribuzione, il supporto per le foto degli utenti è lo stesso di Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="55511-202">If Exchange 2013 is not used in your deployment, support for user photos is the same as with Lync 2010.</span></span> <span data-ttu-id="55511-203">Tuttavia, le opzioni utente per scegliere la foto da utilizzare sono diverse nel client Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="55511-203">However, the user options to choose the photo to use are different in Lync 2013 client.</span></span> <span data-ttu-id="55511-204">Nel client Lync 2013, gli utenti possono scegliere di **nascondere la foto** o di **visualizzare l'immagine**.</span><span class="sxs-lookup"><span data-stu-id="55511-204">In Lync 2013 client, users can select either **Hide my picture** or **Show my picture**.</span></span> <span data-ttu-id="55511-205">L'opzione **Mostra un'immagine da un sito Web** non è disponibile per impostazione predefinita, ma può essere abilitata assegnando un criterio client.</span><span class="sxs-lookup"><span data-stu-id="55511-205">The option **Show a picture from a website** is not available by default, but can be enabled by assigning a client policy.</span></span>

<div>

## <a name="hide-my-picture"></a><span data-ttu-id="55511-206">Nascondi immagine</span><span class="sxs-lookup"><span data-stu-id="55511-206">Hide my picture</span></span>

<span data-ttu-id="55511-207">Le impostazioni per le foto degli utenti sono disponibili nella finestra di dialogo **Opzioni** in Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="55511-207">Settings for user photos are on the **Options** dialog in Lync 2013.</span></span> <span data-ttu-id="55511-208">Quando si sceglie **Nascondi immagine**, non viene visualizzata alcuna foto utente nel client Lync, ma la foto è ancora visualizzata nella scheda contatto e all'esterno di Lync.</span><span class="sxs-lookup"><span data-stu-id="55511-208">When you choose **Hide my picture**, no user photo is displayed for you in Lync client, but your photo is still displayed on your contact card and outside of Lync.</span></span>

</div>

<div>

## <a name="show-my-picture"></a><span data-ttu-id="55511-209">Mostra immagine personale</span><span class="sxs-lookup"><span data-stu-id="55511-209">Show my picture</span></span>

<span data-ttu-id="55511-210">Quando si sceglie l'opzione **Mostra immagine personale** , la foto utente viene visualizzata nel client Lync e ad altri utenti nelle conversazioni di Lync.</span><span class="sxs-lookup"><span data-stu-id="55511-210">When you choose the **Show my picture** option, your user photo is displayed in your Lync client and to other users in Lync conversations.</span></span> <span data-ttu-id="55511-211">L'immagine utilizzata è quella memorizzata in servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="55511-211">The image used is the one stored in AD DS.</span></span>

</div>

<div>

## <a name="show-a-picture-from-a-website"></a><span data-ttu-id="55511-212">Visualizzazione di un'immagine da un sito Web</span><span class="sxs-lookup"><span data-stu-id="55511-212">Show a picture from a website</span></span>

<span data-ttu-id="55511-213">L'opzione **Mostra immagine da un sito Web** diventa disponibile in Lync 2013 dopo che è stato impostato un criterio client per abilitarlo.</span><span class="sxs-lookup"><span data-stu-id="55511-213">The **Show picture from a website** option becomes available in Lync 2013 after a client policy is set to enable it.</span></span> <span data-ttu-id="55511-214">La versione client deve essere più recente di 15.0.4535.1002, che viene installata con gli [aggiornamenti cumulativi di Lync: novembre 2013](https://go.microsoft.com/fwlink/p/?linkid=509908).</span><span class="sxs-lookup"><span data-stu-id="55511-214">The client version must be newer than 15.0.4535.1002, which is installed with the [Lync Cumulative Updates: November 2013](https://go.microsoft.com/fwlink/p/?linkid=509908).</span></span> <span data-ttu-id="55511-215">Gli utenti potrebbero dover disconnettersi e quindi eseguire nuovamente l'accesso per visualizzare le modifiche apportate al client.</span><span class="sxs-lookup"><span data-stu-id="55511-215">Users may need to log out and then back in again to see the changes in the client.</span></span>

<span data-ttu-id="55511-216">È possibile impostare il criterio client in modo da consentire la **visualizzazione di un'immagine da un'impostazione del sito Web** eseguendo il criterio [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) in Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="55511-216">You can set the client policy to enable to **Show picture from a website** setting by running the [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) policy in the Lync Server Management Shell.</span></span> <span data-ttu-id="55511-217">Nei cmdlet di esempio riportati di seguito viene illustrato come impostare il criterio a livello globale per tutti gli utenti nella distribuzione:</span><span class="sxs-lookup"><span data-stu-id="55511-217">The following example cmdlets demonstrate how to set the policy globally for all users in your deployment:</span></span>

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


<span data-ttu-id="55511-218">Quando un'immagine viene caricata nella cassetta postale dell'utente, Exchange crea automaticamente una versione di risoluzione più bassa dell'immagine che può essere utilizzata nelle applicazioni client.</span><span class="sxs-lookup"><span data-stu-id="55511-218">When an image is uploaded to the user’s mailbox, Exchange automatically creates a lower resolution version of the image which can be used in client applications.</span></span> <span data-ttu-id="55511-219">La foto dell'utente viene aggiornata anche in servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="55511-219">The user photo is also updated in AD DS.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="55511-220">Quando un file di immagine viene aggiornato in servizi di dominio Active Directory, viene creata e utilizzata un'immagine di 48 x 48 pixel per il thumbnailPhoto in servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="55511-220">When an image file is updated in AD DS, a 48 x 48 pixel image is created and used for the thumbnailPhoto in AD DS.</span></span> <span data-ttu-id="55511-221">Qualsiasi immagine esistente viene sostituita.</span><span class="sxs-lookup"><span data-stu-id="55511-221">Any existing image is replaced.</span></span> <span data-ttu-id="55511-222">Pertanto, se è stata aggiunta un'immagine di 96 x 96 a servizi di dominio Active Directory, verrà sovrascritta con la nuova immagine 48 x 48.</span><span class="sxs-lookup"><span data-stu-id="55511-222">So if you added a 96 x 96 image to AD DS, it will be overwritten with the new 48 x 48 image.</span></span> <span data-ttu-id="55511-223">Questo è importante solo se si dispone di utenti nell'ambiente che utilizzano client Lync 2010, in quanto tali client otterranno foto utente da servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="55511-223">This is only important is you have users in your environment using Lync 2010 clients, as those clients will obtain user photos from AD DS.</span></span> <span data-ttu-id="55511-224">Se si dispone di client Lync 2010 nell'organizzazione, è possibile importare immagini da 96 x 96 pixel per sostituire quelle create da servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="55511-224">You can import 96 x 96 pixel images to replace the ones created by AD DS if you have Lync 2010 clients in your organization.</span></span>



</div>

</div>

<div>

## <a name="user-photo-support-in-lync-2013"></a><span data-ttu-id="55511-225">Supporto per le foto degli utenti in Lync 2013</span><span class="sxs-lookup"><span data-stu-id="55511-225">User photo support in Lync 2013</span></span>

<span data-ttu-id="55511-226">In Lync 2013, sono supportate tre risoluzioni immagine per le foto degli utenti, come descritto nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="55511-226">In Lync 2013, three image resolutions are supported for user photos as described in the following table.</span></span> <span data-ttu-id="55511-227">L'immagine utilizzata è determinata dall'impostazione del criterio client assegnata agli utenti di Lync.</span><span class="sxs-lookup"><span data-stu-id="55511-227">The image that is used is determined by the client policy setting assigned to Lync users.</span></span> <span data-ttu-id="55511-228">Per ulteriori informazioni, vedere la sezione relativa alla gestione delle foto degli utenti con i cmdlet per i criteri client.</span><span class="sxs-lookup"><span data-stu-id="55511-228">See “Managing user’s photo with Client Policy cmdlets” in this topic for more information.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="55511-229">Risoluzione immagine (pixel)</span><span class="sxs-lookup"><span data-stu-id="55511-229">Image resolution (pixels)</span></span></th>
<th><span data-ttu-id="55511-230">Applicazione</span><span class="sxs-lookup"><span data-stu-id="55511-230">Application</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="55511-231">48 x 48</span><span class="sxs-lookup"><span data-stu-id="55511-231">48 x 48</span></span></p></td>
<td><p><span data-ttu-id="55511-232">Viene utilizzata se non è selezionata alcuna immagine con risoluzione superiore</span><span class="sxs-lookup"><span data-stu-id="55511-232">Used if no higher resolution image is selected</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55511-233">96 x 96</span><span class="sxs-lookup"><span data-stu-id="55511-233">96 x 96</span></span></p></td>
<td><p><span data-ttu-id="55511-234">Utilizzato in Outlook Web App e Outlook 2013</span><span class="sxs-lookup"><span data-stu-id="55511-234">Used in Outlook Web App and Outlook 2013</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="55511-235">648 x 648</span><span class="sxs-lookup"><span data-stu-id="55511-235">648 x 648</span></span></p></td>
<td><p><span data-ttu-id="55511-236">Utilizzato in Lync 2013 client desktop e Lync 2013 Web App</span><span class="sxs-lookup"><span data-stu-id="55511-236">Used in Lync 2013 desktop client and Lync 2013 Web App</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="55511-237">Qualsiasi utente con una cassetta postale abilitata in Exchange 2013 può caricare un'immagine diversa, incluse le foto ad alta risoluzione, tramite le opzioni client di Outlook Web Access o Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="55511-237">Any user with a mailbox enabled in Exchange 2013 can upload a different image, including high-resolution photos, through Outlook Web Access or Lync 2013 client options.</span></span> <span data-ttu-id="55511-238">Le impostazioni consigliate per le immagini utilizzate sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="55511-238">The recommended settings for images used include:</span></span>

  - <span data-ttu-id="55511-239">**Risoluzione**     dell'immagine 648 per 648 pixel</span><span class="sxs-lookup"><span data-stu-id="55511-239">**Image Resolution**   648 by 648 pixels</span></span>

  - <span data-ttu-id="55511-240">**Profondità colore**     a 24 bit</span><span class="sxs-lookup"><span data-stu-id="55511-240">**Color Depth**   24-bit</span></span>

  - <span data-ttu-id="55511-241">Dimensione del file di **immagine**     fino a 20 MB</span><span class="sxs-lookup"><span data-stu-id="55511-241">**Image file size**   up to 20 MB</span></span>

  - <span data-ttu-id="55511-242">**Formato**     di file JPEG</span><span class="sxs-lookup"><span data-stu-id="55511-242">**File format**   JPEG</span></span>

<span data-ttu-id="55511-243">Un'immagine JPEG a 24 bit tipica di 648 pixel per 648 pixel ha dimensioni di un file di circa 240 KB, quindi è necessario un MB di spazio di archiviazione per ogni 4 foto utente.</span><span class="sxs-lookup"><span data-stu-id="55511-243">A typical 24-bit JPEG image that is 648 pixels by 648 pixels has a file size of about 240 KB, so 1 MB of storage space is needed for every 4 user photos.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

