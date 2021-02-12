---
title: Usare Config.xml per eseguire attività di installazione nei client Skype for Business
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 0813184a-ab40-417c-b3a3-c2090766b831
description: 'Riepilogo: informazioni su come utilizzare il Config.xml per specificare istruzioni di installazione aggiuntive.'
ms.openlocfilehash: 1b8aeeb16e061e7816e475f01c9cd9a9146306ee
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825186"
---
# <a name="use-configxml-to-perform-installation-tasks-in-skype-for-business-clients"></a><span data-ttu-id="03c0d-103">Usare Config.xml per eseguire attività di installazione nei client Skype for Business</span><span class="sxs-lookup"><span data-stu-id="03c0d-103">Use Config.xml to perform installation tasks in Skype for Business clients</span></span>

<span data-ttu-id="03c0d-104">**Riepilogo:** Come usare il file Config.xml per specificare istruzioni di installazione aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="03c0d-104">**Summary:** How to use the Config.xml file to specify additional installation instructions.</span></span>

<span data-ttu-id="03c0d-105">Sebbene lo Strumento di personalizzazione di Office sia lo strumento principale per l'installazione della personalizzazione, gli amministratori possono utilizzare il file Config.xml per specificare istruzioni di installazione aggiuntive non disponibili nello Strumento di personalizzazione di Office.</span><span class="sxs-lookup"><span data-stu-id="03c0d-105">Although the Office Customization Tool (OCT) is the primary tool for customization installation, administrators can use the Config.xml file to specify additional installation instructions that are not available in the OCT.</span></span> <span data-ttu-id="03c0d-106">È possibile eseguire le personalizzazioni seguenti solo mediante il file Config.xml:</span><span class="sxs-lookup"><span data-stu-id="03c0d-106">The following customizations can only be made by using the Config.xml file:</span></span>

- <span data-ttu-id="03c0d-107">Specificare il percorso del punto di installazione di rete.</span><span class="sxs-lookup"><span data-stu-id="03c0d-107">Specify the path of the network installation point.</span></span>

- <span data-ttu-id="03c0d-108">Selezionare i prodotti da installare.</span><span class="sxs-lookup"><span data-stu-id="03c0d-108">Select the products to install.</span></span>

- <span data-ttu-id="03c0d-109">Configurare la registrazione e il percorso del file di personalizzazione dell'installazione e degli aggiornamenti software.</span><span class="sxs-lookup"><span data-stu-id="03c0d-109">Configure logging and the location of the Setup customization file and software updates.</span></span>

- <span data-ttu-id="03c0d-110">Specificare le opzioni di installazione, ad esempio il nome utente.</span><span class="sxs-lookup"><span data-stu-id="03c0d-110">Specify installation options, such as user name.</span></span>

- <span data-ttu-id="03c0d-111">Copiare l'origine di installazione locale nel computer dell'utente senza installare Office.</span><span class="sxs-lookup"><span data-stu-id="03c0d-111">Copy the local installation source (LIS) to the user's computer without installing Office.</span></span>

- <span data-ttu-id="03c0d-112">Aggiungere o rimuovere lingue dall'installazione.</span><span class="sxs-lookup"><span data-stu-id="03c0d-112">Add or remove languages from the installation.</span></span>

<span data-ttu-id="03c0d-113">Si consiglia di utilizzare il file di Config.xml per configurare l'installazione di Skype for Business invisibile all'utente.</span><span class="sxs-lookup"><span data-stu-id="03c0d-113">We recommend that you use the Config.xml file to configure Skype for Business silent installation.</span></span> 

<span data-ttu-id="03c0d-114">Per impostazione predefinita, Config.xml file archiviato nella cartella di base del prodotto (ad esempio, \ _product_. WW) indica al programma di installazione di installare il prodotto.</span><span class="sxs-lookup"><span data-stu-id="03c0d-114">By default, the Config.xml file that is stored in the core product folder (for example, \ _product_.WW) directs Setup to install that product.</span></span> <span data-ttu-id="03c0d-115">Ad esempio, il file Config.xml nella cartella seguente installa Skype for Business:</span><span class="sxs-lookup"><span data-stu-id="03c0d-115">For example, the Config.xml file in the following folder installs Skype for Business:</span></span>

- <span data-ttu-id="03c0d-116">\\server\share\Skype15\Skype.WW \Config.xml</span><span class="sxs-lookup"><span data-stu-id="03c0d-116">\\server\share\Skype15\Skype.WW \Config.xml</span></span>

<span data-ttu-id="03c0d-117">Gli Config.xml più comunemente utilizzati per l'installazione di Skype for Business sono elencati nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="03c0d-117">The Config.xml elements most commonly used for Skype for Business installation are listed in the following table.</span></span>

<span data-ttu-id="03c0d-118">**Config.xml elementi**</span><span class="sxs-lookup"><span data-stu-id="03c0d-118">**Config.xml elements**</span></span>


| <span data-ttu-id="03c0d-119">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="03c0d-119">**Element**</span></span>              | <span data-ttu-id="03c0d-120">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="03c0d-120">**Description**</span></span>                                                                                                                                                                                                                                                                                         |
|:-------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="03c0d-121">Configurazione</span><span class="sxs-lookup"><span data-stu-id="03c0d-121">Configuration</span></span>  <br/>     | <span data-ttu-id="03c0d-122">Elemento di primo livello (obbligatorio).</span><span class="sxs-lookup"><span data-stu-id="03c0d-122">Top-level element (required).</span></span> <span data-ttu-id="03c0d-123">Contiene l'attributo Product, ad esempio: Product=Lync (funzionerà per i client Skype for Business)</span><span class="sxs-lookup"><span data-stu-id="03c0d-123">Contains the Product attribute, for example: Product=Lync (This will work for Skype for Business clients)</span></span>  <br/>                                                                                                                                                          |
| <span data-ttu-id="03c0d-124">OptionState</span><span class="sxs-lookup"><span data-stu-id="03c0d-124">OptionState</span></span>  <br/>       | <span data-ttu-id="03c0d-125">Specifica come vengono gestite caratteristiche specifiche del prodotto durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="03c0d-125">Specifies how specific product features are handled during installation.</span></span> <span data-ttu-id="03c0d-126">Utilizzare gli attributi seguenti per impedire l'installazione di Servizi di integrazione applicativa, che include componenti condivisi che interferiscono con Outlook:</span><span class="sxs-lookup"><span data-stu-id="03c0d-126">Use the following attributes to prevent installation of Business Connectivity Services, which includes shared components that interfere with Outlook:</span></span> <br/>  <span data-ttu-id="03c0d-127">Id="LOBiMain"</span><span class="sxs-lookup"><span data-stu-id="03c0d-127">Id="LOBiMain"</span></span> <br/>  <span data-ttu-id="03c0d-128">State="Absent"</span><span class="sxs-lookup"><span data-stu-id="03c0d-128">State="Absent"</span></span> <br/>  <span data-ttu-id="03c0d-129">Children="Force"</span><span class="sxs-lookup"><span data-stu-id="03c0d-129">Children="Force"</span></span> <br/> |
| <span data-ttu-id="03c0d-130">Visualizza</span><span class="sxs-lookup"><span data-stu-id="03c0d-130">Display</span></span>  <br/>           | <span data-ttu-id="03c0d-131">Livello di interfaccia utente visualizzato all'utente dal programma di installazione.</span><span class="sxs-lookup"><span data-stu-id="03c0d-131">The level of UI that Setup displays to the user.</span></span> <span data-ttu-id="03c0d-132">Di seguito sono riportati alcuni attributi tipici:</span><span class="sxs-lookup"><span data-stu-id="03c0d-132">Typical attributes include the following:</span></span> <br/>  <span data-ttu-id="03c0d-133">CompletionNotice="Yes"</span><span class="sxs-lookup"><span data-stu-id="03c0d-133">CompletionNotice="Yes"</span></span>                                                                                                                                                                                |
| <span data-ttu-id="03c0d-134">Registrazione</span><span class="sxs-lookup"><span data-stu-id="03c0d-134">Logging</span></span>  <br/>           | <span data-ttu-id="03c0d-135">Opzioni per il tipo di registrazione eseguito dal programma di installazione.</span><span class="sxs-lookup"><span data-stu-id="03c0d-135">Options for the kind of logging that Setup performs.</span></span> <span data-ttu-id="03c0d-136">Di seguito sono riportati alcuni attributi tipici:</span><span class="sxs-lookup"><span data-stu-id="03c0d-136">Typical attributes include the following:</span></span> <br/>  <span data-ttu-id="03c0d-137">Type ="Off"</span><span class="sxs-lookup"><span data-stu-id="03c0d-137">Type ="Off"</span></span>                                                                                                                                                                                       |
| <span data-ttu-id="03c0d-138">Impostazione</span><span class="sxs-lookup"><span data-stu-id="03c0d-138">Setting</span></span>  <br/>           | <span data-ttu-id="03c0d-139">Specifica i valori per le proprietà di Windows Installer.</span><span class="sxs-lookup"><span data-stu-id="03c0d-139">Specifies values for Windows Installer properties.</span></span> <span data-ttu-id="03c0d-140">Di seguito sono riportati alcuni attributi tipici:</span><span class="sxs-lookup"><span data-stu-id="03c0d-140">Typical attributes include the following:</span></span> <br/>  <span data-ttu-id="03c0d-141">Setting Id=" *name*" (nome della proprietà di Windows Installer)</span><span class="sxs-lookup"><span data-stu-id="03c0d-141">Setting Id=" *name*" (the name of the Windows Installer property)</span></span>  <br/>  <span data-ttu-id="03c0d-142">Valore=" *valore*" (valore da assegnare alla proprietà)</span><span class="sxs-lookup"><span data-stu-id="03c0d-142">Value=" *value*" (the value to assign to the property)</span></span>  <br/>                                                             |
| <span data-ttu-id="03c0d-143">DistributionPoint</span><span class="sxs-lookup"><span data-stu-id="03c0d-143">DistributionPoint</span></span>  <br/> | <span data-ttu-id="03c0d-144">Percorso completo del punto di installazione di rete da cui deve essere eseguita l'installazione</span><span class="sxs-lookup"><span data-stu-id="03c0d-144">The fully qualified path of the network installation point from which the installation is to run.</span></span> <span data-ttu-id="03c0d-145">Include l'attributo Location:</span><span class="sxs-lookup"><span data-stu-id="03c0d-145">Includes the Location attribute:</span></span> <br/>  <span data-ttu-id="03c0d-146">Percorso=" *percorso*"</span><span class="sxs-lookup"><span data-stu-id="03c0d-146">Location=" *path*"</span></span>  <br/>                                                                                                                                     |

<span data-ttu-id="03c0d-147">L'esempio seguente mostra un file Config.xml per un'installazione invisibile all'utente tipica del client Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="03c0d-147">The following example shows a Config.xml file for a typical silent installation of the Skype for Business client.</span></span> 

```xml
<Configuration Product="Lync"> 
  <OptionState Id="LOBiMain" State="Absent" Children="Force" /> 
  <Display Level="None" CompletionNotice="No" AcceptEula="Yes" /> 
  <Logging Type="verbose" Path="%temp%" Template="LyncSetupVerbose(*).log" />
  <Setting Id="SETUP_REBOOT" Value="Never" /> 
  <DistributionPoint Location="\\server\share\Skype15" /> 
</Configuration>
```

<span data-ttu-id="03c0d-148">Informazioni dettagliate sull'utilizzo del file Config.xml per eseguire le attività di installazione e manutenzione di Office sono disponibili all'indirizzo [https://go.microsoft.com/fwlink/p/?linkid=267514](https://go.microsoft.com/fwlink/p/?linkid=267514) .</span><span class="sxs-lookup"><span data-stu-id="03c0d-148">Detailed information about using the Config.xml file to perform Office installation and maintenance tasks is available at [https://go.microsoft.com/fwlink/p/?linkid=267514](https://go.microsoft.com/fwlink/p/?linkid=267514).</span></span>

## <a name="to-customize-the-configxml-file"></a><span data-ttu-id="03c0d-149">Per personalizzare il Config.xml file</span><span class="sxs-lookup"><span data-stu-id="03c0d-149">To customize the Config.xml file</span></span>

1. <span data-ttu-id="03c0d-150">Aprire il Config.xml file utilizzando uno strumento di editor di testo, ad esempio Blocco note.</span><span class="sxs-lookup"><span data-stu-id="03c0d-150">Open the Config.xml file by using a text editor tool, such as Notepad.</span></span>

2. <span data-ttu-id="03c0d-151">Individuare le righe che contengono gli elementi che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="03c0d-151">Locate the lines that contain the elements you want to change.</span></span>

3. <span data-ttu-id="03c0d-152">Modificare la voce dell'elemento con le opzioni invisibile all'utente che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="03c0d-152">Modify the element entry with the silent options that you want to use.</span></span> <span data-ttu-id="03c0d-153">Assicurarsi di rimuovere i delimitatori di commento" \<!--" and "--\> ".</span><span class="sxs-lookup"><span data-stu-id="03c0d-153">Make sure that you remove the comment delimiters, "\<!--" and "--\>".</span></span> <span data-ttu-id="03c0d-154">Utilizzare ad esempio la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="03c0d-154">For example, use the following syntax:</span></span>

   <pre>
   < DistributionPoint Location="\\server\share\Skype15" />
   </pre>

4. <span data-ttu-id="03c0d-155">Salvare il file Config.xml.</span><span class="sxs-lookup"><span data-stu-id="03c0d-155">Save the Config.xml file.</span></span>


