---
title: USA config. XML per eseguire attività di installazione nei client Skype for business
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0813184a-ab40-417c-b3a3-c2090766b831
description: "Riepilogo: come usare il file config. XML per specificare altre istruzioni per l'installazione."
ms.openlocfilehash: 31ee6c663822c2dab59a21fe5ca80c71cb81abf8
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234823"
---
# <a name="use-configxml-to-perform-installation-tasks-in-skype-for-business-clients"></a><span data-ttu-id="996a5-103">USA config. XML per eseguire attività di installazione nei client Skype for business</span><span class="sxs-lookup"><span data-stu-id="996a5-103">Use Config.xml to perform installation tasks in Skype for Business clients</span></span>

<span data-ttu-id="996a5-104">**Riepilogo:** Come usare il file config. XML per specificare altre istruzioni per l'installazione.</span><span class="sxs-lookup"><span data-stu-id="996a5-104">**Summary:** How to use the Config.xml file to specify additional installation instructions.</span></span>

<span data-ttu-id="996a5-105">Anche se lo strumento di personalizzazione di Office (OCT) è lo strumento principale per l'installazione di personalizzazione, gli amministratori possono usare il file config. XML per specificare altre istruzioni per l'installazione che non sono disponibili in ottobre.</span><span class="sxs-lookup"><span data-stu-id="996a5-105">Although the Office Customization Tool (OCT) is the primary tool for customization installation, administrators can use the Config.xml file to specify additional installation instructions that are not available in the OCT.</span></span> <span data-ttu-id="996a5-106">Le personalizzazioni seguenti possono essere eseguite solo usando il file config. XML:</span><span class="sxs-lookup"><span data-stu-id="996a5-106">The following customizations can only be made by using the Config.xml file:</span></span>

- <span data-ttu-id="996a5-107">Specificare il percorso del punto di installazione della rete.</span><span class="sxs-lookup"><span data-stu-id="996a5-107">Specify the path of the network installation point.</span></span>

- <span data-ttu-id="996a5-108">Selezionare i prodotti da installare.</span><span class="sxs-lookup"><span data-stu-id="996a5-108">Select the products to install.</span></span>

- <span data-ttu-id="996a5-109">Configurare la registrazione e la posizione del file di personalizzazione della configurazione e degli aggiornamenti software.</span><span class="sxs-lookup"><span data-stu-id="996a5-109">Configure logging and the location of the Setup customization file and software updates.</span></span>

- <span data-ttu-id="996a5-110">Specificare le opzioni di installazione, ad esempio nome utente.</span><span class="sxs-lookup"><span data-stu-id="996a5-110">Specify installation options, such as user name.</span></span>

- <span data-ttu-id="996a5-111">Copiare l'origine di installazione locale (LIS) nel computer dell'utente senza installare Office.</span><span class="sxs-lookup"><span data-stu-id="996a5-111">Copy the local installation source (LIS) to the user's computer without installing Office.</span></span>

- <span data-ttu-id="996a5-112">Aggiungere o rimuovere lingue dall'installazione.</span><span class="sxs-lookup"><span data-stu-id="996a5-112">Add or remove languages from the installation.</span></span>

<span data-ttu-id="996a5-113">Ti consigliamo di usare il file config. XML per configurare l'installazione silenziosa di Skype for business.</span><span class="sxs-lookup"><span data-stu-id="996a5-113">We recommend that you use the Config.xml file to configure Skype for Business silent installation.</span></span> 

<span data-ttu-id="996a5-114">Per impostazione predefinita, il file config. xml archiviato nella cartella principale del prodotto, ad esempio \ _Product_. WW) indirizza la configurazione per l'installazione di tale prodotto.</span><span class="sxs-lookup"><span data-stu-id="996a5-114">By default, the Config.xml file that is stored in the core product folder (for example, \ _product_.WW) directs Setup to install that product.</span></span> <span data-ttu-id="996a5-115">Ad esempio, il file config. XML nella cartella seguente installa Skype for business:</span><span class="sxs-lookup"><span data-stu-id="996a5-115">For example, the Config.xml file in the following folder installs Skype for Business:</span></span>

- <span data-ttu-id="996a5-116">\\server\share\Skype15\Skype.WW \Config.xml</span><span class="sxs-lookup"><span data-stu-id="996a5-116">\\server\share\Skype15\Skype.WW \Config.xml</span></span>

<span data-ttu-id="996a5-117">Gli elementi config. XML usati più comunemente per l'installazione di Skype for business sono elencati nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="996a5-117">The Config.xml elements most commonly used for Skype for Business installation are listed in the following table.</span></span>

<span data-ttu-id="996a5-118">**Elementi config. XML**</span><span class="sxs-lookup"><span data-stu-id="996a5-118">**Config.xml elements**</span></span>


| <span data-ttu-id="996a5-119">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="996a5-119">**Element**</span></span>              | <span data-ttu-id="996a5-120">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="996a5-120">**Description**</span></span>                                                                                                                                                                                                                                                                                         |
|:-------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="996a5-121">Configurazione</span><span class="sxs-lookup"><span data-stu-id="996a5-121">Configuration</span></span>  <br/>     | <span data-ttu-id="996a5-122">Elemento di primo livello (obbligatorio).</span><span class="sxs-lookup"><span data-stu-id="996a5-122">Top-level element (required).</span></span> <span data-ttu-id="996a5-123">Contiene l'attributo Product, ad esempio: Product = Lync (questo funzionerà per i client Skype for business)</span><span class="sxs-lookup"><span data-stu-id="996a5-123">Contains the Product attribute, for example: Product=Lync (This will work for Skype for Business clients)</span></span>  <br/>                                                                                                                                                          |
| <span data-ttu-id="996a5-124">OptionState</span><span class="sxs-lookup"><span data-stu-id="996a5-124">OptionState</span></span>  <br/>       | <span data-ttu-id="996a5-125">Specifica il modo in cui vengono gestite le caratteristiche specifiche del prodotto durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="996a5-125">Specifies how specific product features are handled during installation.</span></span> <span data-ttu-id="996a5-126">Usare gli attributi seguenti per impedire l'installazione di servizi di integrazione applicativa, che includono componenti condivisi che interferiscono con Outlook:</span><span class="sxs-lookup"><span data-stu-id="996a5-126">Use the following attributes to prevent installation of Business Connectivity Services, which includes shared components that interfere with Outlook:</span></span> <br/>  <span data-ttu-id="996a5-127">ID = "LOBiMain"</span><span class="sxs-lookup"><span data-stu-id="996a5-127">Id="LOBiMain"</span></span> <br/>  <span data-ttu-id="996a5-128">Stato = "assente"</span><span class="sxs-lookup"><span data-stu-id="996a5-128">State="Absent"</span></span> <br/>  <span data-ttu-id="996a5-129">Children = "forza"</span><span class="sxs-lookup"><span data-stu-id="996a5-129">Children="Force"</span></span> <br/> |
| <span data-ttu-id="996a5-130">Visualizzare</span><span class="sxs-lookup"><span data-stu-id="996a5-130">Display</span></span>  <br/>           | <span data-ttu-id="996a5-131">Il livello di interfaccia utente visualizzato per l'installazione per l'utente.</span><span class="sxs-lookup"><span data-stu-id="996a5-131">The level of UI that Setup displays to the user.</span></span> <span data-ttu-id="996a5-132">Gli attributi tipici includono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="996a5-132">Typical attributes include the following:</span></span> <br/>  <span data-ttu-id="996a5-133">CompletionNotice = "Sì"</span><span class="sxs-lookup"><span data-stu-id="996a5-133">CompletionNotice="Yes"</span></span>                                                                                                                                                                                |
| <span data-ttu-id="996a5-134">Registrazione</span><span class="sxs-lookup"><span data-stu-id="996a5-134">Logging</span></span>  <br/>           | <span data-ttu-id="996a5-135">Opzioni per il tipo di registrazione eseguito dall'installazione.</span><span class="sxs-lookup"><span data-stu-id="996a5-135">Options for the kind of logging that Setup performs.</span></span> <span data-ttu-id="996a5-136">Gli attributi tipici includono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="996a5-136">Typical attributes include the following:</span></span> <br/>  <span data-ttu-id="996a5-137">Digitare = "disattivato"</span><span class="sxs-lookup"><span data-stu-id="996a5-137">Type ="Off"</span></span>                                                                                                                                                                                       |
| <span data-ttu-id="996a5-138">Impostazione</span><span class="sxs-lookup"><span data-stu-id="996a5-138">Setting</span></span>  <br/>           | <span data-ttu-id="996a5-139">Specifica i valori per le proprietà di Windows Installer.</span><span class="sxs-lookup"><span data-stu-id="996a5-139">Specifies values for Windows Installer properties.</span></span> <span data-ttu-id="996a5-140">Gli attributi tipici includono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="996a5-140">Typical attributes include the following:</span></span> <br/>  <span data-ttu-id="996a5-141">Setting ID = " *Name*" (il nome della proprietà di Windows Installer)</span><span class="sxs-lookup"><span data-stu-id="996a5-141">Setting Id=" *name*" (the name of the Windows Installer property)</span></span>  <br/>  <span data-ttu-id="996a5-142">Value = " *value*" (il valore da assegnare alla proprietà)</span><span class="sxs-lookup"><span data-stu-id="996a5-142">Value=" *value*" (the value to assign to the property)</span></span>  <br/>                                                             |
| <span data-ttu-id="996a5-143">DistributionPoint</span><span class="sxs-lookup"><span data-stu-id="996a5-143">DistributionPoint</span></span>  <br/> | <span data-ttu-id="996a5-144">Percorso completo del punto di installazione di rete da cui eseguire l'installazione.</span><span class="sxs-lookup"><span data-stu-id="996a5-144">The fully qualified path of the network installation point from which the installation is to run.</span></span> <span data-ttu-id="996a5-145">Include l'attributo location:</span><span class="sxs-lookup"><span data-stu-id="996a5-145">Includes the Location attribute:</span></span> <br/>  <span data-ttu-id="996a5-146">Location = " *path*"</span><span class="sxs-lookup"><span data-stu-id="996a5-146">Location=" *path*"</span></span>  <br/>                                                                                                                                     |

<span data-ttu-id="996a5-147">L'esempio seguente mostra un file config. XML per una tipica installazione silenziosa del client Skype for business.</span><span class="sxs-lookup"><span data-stu-id="996a5-147">The following example shows a Config.xml file for a typical silent installation of the Skype for Business client.</span></span> 

```
<Configuration Product="Lync"> 
  <OptionState Id="LOBiMain" State="Absent" Children="Force" /> 
  <Display Level="None" CompletionNotice="No" AcceptEula="Yes" /> 
  <Logging Type="verbose" Path="%temp%" Template="LyncSetupVerbose(*).log" />
  <Setting Id="SETUP_REBOOT" Value="Never" /> 
  <DistributionPoint Location="\\server\share\Skype15" /> 
</Configuration>
```

<span data-ttu-id="996a5-148">Informazioni dettagliate sull'uso del file config. XML per eseguire attività di installazione e manutenzione di Office sono [https://go.microsoft.com/fwlink/p/?linkid=267514](https://go.microsoft.com/fwlink/p/?linkid=267514)disponibili all'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="996a5-148">Detailed information about using the Config.xml file to perform Office installation and maintenance tasks is available at [https://go.microsoft.com/fwlink/p/?linkid=267514](https://go.microsoft.com/fwlink/p/?linkid=267514).</span></span>

## <a name="to-customize-the-configxml-file"></a><span data-ttu-id="996a5-149">Per personalizzare il file config. XML</span><span class="sxs-lookup"><span data-stu-id="996a5-149">To customize the Config.xml file</span></span>

1. <span data-ttu-id="996a5-150">Aprire il file config. XML usando uno strumento di editor di testo, ad esempio Blocco note.</span><span class="sxs-lookup"><span data-stu-id="996a5-150">Open the Config.xml file by using a text editor tool, such as Notepad.</span></span>

2. <span data-ttu-id="996a5-151">Individuare le righe che contengono gli elementi che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="996a5-151">Locate the lines that contain the elements you want to change.</span></span>

3. <span data-ttu-id="996a5-152">Modificare la voce dell'elemento con le opzioni Silent che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="996a5-152">Modify the element entry with the silent options that you want to use.</span></span> <span data-ttu-id="996a5-153">Assicurarsi di rimuovere i delimitatori di commento, "\<!--" e "--\>".</span><span class="sxs-lookup"><span data-stu-id="996a5-153">Make sure that you remove the comment delimiters, "\<!--" and "--\>".</span></span> <span data-ttu-id="996a5-154">Ad esempio, usare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="996a5-154">For example, use the following syntax:</span></span>

   <pre>
   < DistributionPoint Location="\\server\share\Skype15" />
   </pre>

4. <span data-ttu-id="996a5-155">Salvare il file config. XML.</span><span class="sxs-lookup"><span data-stu-id="996a5-155">Save the Config.xml file.</span></span>


