---
title: Configurare l'uso di foto ad alta risoluzione in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 995da78a-dc44-45a3-908d-16fe36cfa0d9
description: "Riepilogo: configurare l'utilizzo di foto ad alta risoluzione in Exchange Server 2019, Exchange Server 2016, Exchange Server 2013 o Exchange Online e Skype for Business Server."
ms.openlocfilehash: f5cc44f9f390c1d3241e7fae68054754ff7b0f76
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109802"
---
# <a name="configure-the-use-of-high-resolution-photos-in-skype-for-business-server"></a><span data-ttu-id="ea7fb-103">Configurare l'uso di foto ad alta risoluzione in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="ea7fb-103">Configure the use of high-resolution photos in Skype for Business Server</span></span>
 
<span data-ttu-id="ea7fb-104">**Riepilogo:** Configurare l'uso di foto ad alta risoluzione in Exchange Server 2019, Exchange Server 2016, Exchange Server 2013 o Exchange Online e Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="ea7fb-104">**Summary:** Configure the use of high-resolution photos in Exchange Server 2019, Exchange Server 2016, Exchange Server 2013, or Exchange Online and Skype for Business Server.</span></span>
  
<span data-ttu-id="ea7fb-105">In Skype for Business Server, le foto possono essere archiviate nella cassetta postale di Exchange Server 2019, Exchange Server 2016, Exchange Server 2013 o Exchange Online, che consente dimensioni delle foto fino a 648 pixel per 648 pixel.</span><span class="sxs-lookup"><span data-stu-id="ea7fb-105">In Skype for Business Server, photos can be stored in a user's Exchange Server 2019, Exchange Server 2016, Exchange Server 2013, or Exchange Online mailbox, which allows for photo sizes up to 648 pixels by 648 pixels.</span></span> <span data-ttu-id="ea7fb-106">Inoltre, Exchange Server ridimensionare automaticamente queste foto per l'uso in prodotti diversi in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="ea7fb-106">In addition, Exchange Server can automatically resize these photos for use in different products as needed.</span></span> <span data-ttu-id="ea7fb-107">Questo significa in genere tre diverse dimensioni e risoluzioni delle foto:</span><span class="sxs-lookup"><span data-stu-id="ea7fb-107">Typically that means three different photo sizes and resolutions:</span></span>
  
- <span data-ttu-id="ea7fb-108">64 pixel per 64 pixel, le dimensioni usate per l'attributo thumbnailPhoto di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ea7fb-108">64 pixels by 64 pixels, the size used for the Active Directory thumbnailPhoto attribute.</span></span> <span data-ttu-id="ea7fb-109">Se si carica una foto in Exchange Server, Exchange creerà automaticamente una versione di 64 pixel per 64 pixel di tale foto e aggiornerà l'attributo thumbnailPhoto dell'utente.</span><span class="sxs-lookup"><span data-stu-id="ea7fb-109">If you upload a photo to Exchange Server, Exchange will automatically create a 64 pixel by 64 pixel version of that photo and update the user's thumbnailPhoto attribute.</span></span> <span data-ttu-id="ea7fb-110">Si noti, tuttavia, che il contrario non è vero: se si aggiorna manualmente l'attributo thumbnailPhoto in Active Directory, la foto nella cassetta postale di Exchange dell'utente non verrà aggiornata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="ea7fb-110">Note, however, that the reverse is not true: if you manually update the thumbnailPhoto attribute in Active Directory the photo in the user's Exchange mailbox will not automatically be updated.</span></span>
    
- <span data-ttu-id="ea7fb-111">96 pixel per 96 pixel, da utilizzare in Microsoft Outlook 2013 Web App, Microsoft Outlook 2013, Skype for Business Web App e Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="ea7fb-111">96 pixels by 96 pixels, for use in Microsoft Outlook 2013 Web App, Microsoft Outlook 2013, Skype for Business Web App, and Skype for Business.</span></span>
    
- <span data-ttu-id="ea7fb-112">648 pixel per 648 pixel per l'uso in Skype for Business e Skype for Business Web App Skype for Business Web App.</span><span class="sxs-lookup"><span data-stu-id="ea7fb-112">648 pixels by 648 pixels for use in Skype for Business and Skype for Business Web App Skype for Business Web App.</span></span>
    
> [!NOTE]
> <span data-ttu-id="ea7fb-113">Se si dispone delle risorse, è consigliabile caricare foto 648 x 648; che offre la massima risoluzione e la qualità ottimale delle immagini in qualsiasi applicazione di Office 2013.</span><span class="sxs-lookup"><span data-stu-id="ea7fb-113">If you have the resources, it is recommended that you upload 648 x 648 photos; that provides the maximum resolution and optimal picture quality in any of the Office 2013 applications.</span></span> <span data-ttu-id="ea7fb-114">Ogni foto JPEG con una dimensione di 648 x 648 e una profondità di 24 bit determina una dimensione del file di circa 240 kilobyte.</span><span class="sxs-lookup"><span data-stu-id="ea7fb-114">Each JPEG photo with a size of 648 x 648 and a depth of 24 bits results in a file size of approximately 240 kilobytes.</span></span> <span data-ttu-id="ea7fb-115">Ciò significa che sarà necessario circa 1 megabyte di spazio su disco per ogni 4 foto di utenti.</span><span class="sxs-lookup"><span data-stu-id="ea7fb-115">That means you will need approximately 1 megabyte of disk space for every 4 user photos.</span></span> 
  
<span data-ttu-id="ea7fb-116">Le foto ad alta risoluzione, a cui si accede tramite Servizi Web Exchange, possono essere caricate dagli utenti che eseguono Outlook 2013 Web App; gli utenti possono solo aggiornare la propria foto.</span><span class="sxs-lookup"><span data-stu-id="ea7fb-116">High-resolution photos, which are accessed by using Exchange Web Services, can be uploaded by users who are running Outlook 2013 Web App; users are only allowed to update their own photo.</span></span> <span data-ttu-id="ea7fb-117">Gli amministratori, tuttavia, possono aggiornare la foto per qualsiasi utente utilizzando Exchange Management Shell e una serie di comandi Windows PowerShell simili ai seguenti:</span><span class="sxs-lookup"><span data-stu-id="ea7fb-117">Administrators, however, can update the photo for any user by using the Exchange Management Shell and a series of Windows PowerShell commands similar to the following:</span></span>
  
```powershell
$photo = ([Byte[]] $(Get-Content -Path "C:\Photos\Kenmyer.jpg" -Encoding Byte -ReadCount 0))
Set-UserPhoto -Identity "Ken Myer" -PictureData $photo -Preview -Confirm:$False
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

<span data-ttu-id="ea7fb-118">Nel primo comando dell'esempio precedente viene utilizzato il cmdlet per leggere il contenuto del file C:\Photos\Kenmyer.jpg e archiviare tali dati in una variabile denominata `Get-Content` $photo.</span><span class="sxs-lookup"><span data-stu-id="ea7fb-118">The first command in the preceding example uses the `Get-Content` cmdlet to read the contents of the file C:\Photos\Kenmyer.jpg and store that data in a variable named $photo.</span></span> <span data-ttu-id="ea7fb-119">Nel secondo comando viene utilizzato il cmdlet Exchange per caricare la foto e allegarlo `Set-UserPhoto` all'account utente di Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="ea7fb-119">In the second command, the Exchange cmdlet `Set-UserPhoto` is used to upload the photo and attach that photo to Ken Myer's user account.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ea7fb-120">In questo esempio, il nome visualizzato di Active Directory di Ken Myer è utilizzato come identità dell'account utente.</span><span class="sxs-lookup"><span data-stu-id="ea7fb-120">In this example, Ken Myer's Active Directory display name is used as the user account Identity.</span></span> <span data-ttu-id="ea7fb-121">È anche possibile fare riferimento a un account utente mediante altri identificatori quali l'indirizzo SMTP dell'utente oppure il relativo nome dell'entità utente.</span><span class="sxs-lookup"><span data-stu-id="ea7fb-121">You can also reference a user account by using other identifiers such as the user's SMTP address or his or her User Principal Name.</span></span> <span data-ttu-id="ea7fb-122">Per ulteriori informazioni, vedere la documentazione Set-UserPhoto cmdlet di configurazione [https://go.microsoft.com/fwlink/p/?LinkId=268536](/powershell/module/exchange/set-userphoto)</span><span class="sxs-lookup"><span data-stu-id="ea7fb-122">See the documentation for the Set-UserPhoto cmdlet at [https://go.microsoft.com/fwlink/p/?LinkId=268536](/powershell/module/exchange/set-userphoto) for more information</span></span>
  
<span data-ttu-id="ea7fb-p107">Il caricamento della foto non equivale ad assegnarla all'account utente di Ken Myer. Esso infatti produce semplicemente un'anteprima della foto da visualizzare nella pagina Opzioni di Outlook Web App. Per assegnare effettivamente la foto all'account utente, quest'ultimo deve fare clic su **Salva** nella pagina Opzioni oppure l'amministratore deve eseguire il terzo comando nell'esempio. Il terzo comando usa il parametro Save per assegnare la foto all'account utente di Ken Myer:</span><span class="sxs-lookup"><span data-stu-id="ea7fb-p107">Uploading the photo does not equate to assigning that photo to Ken Myer's user account. Instead, uploading the photo simply results in a preview of that photo to be displayed on the Outlook Web App Options page. To actually assign that photo to the user account the user must click **Save** on the Options page or the administrator must execute the third command in the example. That third command uses the Save parameter to assign the photo to Ken Myer's user account:</span></span>
  
```powershell
Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False
```

<span data-ttu-id="ea7fb-127">Per verificare che la nuova foto sia stata assegnata all'account utente, Ken Myer può accedere a Skype for Business, selezionare **Opzioni** e quindi Selezionare **Immagine personale.**</span><span class="sxs-lookup"><span data-stu-id="ea7fb-127">To verify that the new photo has been assigned to the user account, Ken Myer can log on to Skype for Business, select **Options**, and then select **My Picture**.</span></span> <span data-ttu-id="ea7fb-128">La nuova foto aggiunta deve essere visualizzata come foto personale di Ken.</span><span class="sxs-lookup"><span data-stu-id="ea7fb-128">The newly-uploaded photo should be displayed as Ken's personal photo.</span></span> <span data-ttu-id="ea7fb-129">In alternativa, gli amministratori possono verificare la foto per qualsiasi utenti avviando Internet Explorer e passando a un URL analogo a questo:</span><span class="sxs-lookup"><span data-stu-id="ea7fb-129">Alternatively, administrators can verify the photo for any user by starting Internet Explorer and navigating to a URL similar to this:</span></span>
  
```console
https://atl-mail-001.litwareinc.com/ews/Exchange.asmx/s/GetUserPhoto?email=kenmyer@litwareinc.com&size=HR648x648
```

<span data-ttu-id="ea7fb-130">Se l'amministratore può visualizzare la foto utilizzando Internet Explorer, ma l'utente non può visualizzare la propria foto in Skype for Business, potrebbe verificarsi un problema di connettività con i servizi Web di Exchange o con il servizio di individuazione automatica di Exchange.</span><span class="sxs-lookup"><span data-stu-id="ea7fb-130">If the administrator can view the photo using Internet Explorer but the user cannot view his or her photo in Skype for Business there may be a connectivity problem with Exchange Web Services or with the Exchange autodiscover service.</span></span>
  
<span data-ttu-id="ea7fb-131">Nota anche che non è necessaria alcuna configurazione aggiuntiva per rendere questa foto disponibile in Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="ea7fb-131">Note, too that no additional configuration is required in order to make this photo available in Skype for Business.</span></span> <span data-ttu-id="ea7fb-132">Al contrario, la foto sarà immediatamente disponibile dopo il caricamento e `Set-UserPhoto` l'esecuzione del cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ea7fb-132">Instead, the photo will be instantly available after it has been uploaded and the `Set-UserPhoto` cmdlet has been run.</span></span>