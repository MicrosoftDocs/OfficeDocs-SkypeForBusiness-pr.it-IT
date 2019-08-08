---
title: Usare le opzioni della riga di comando di configurazione con i client Skype for business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
description: 'Riepilogo: informazioni sulle operazioni della riga di comando Setup. exe in configurazione di Office.'
ms.openlocfilehash: a84c1f8a69bdff07dfec5e274932a522bf139c9a
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234836"
---
# <a name="use-setup-command-line-options-with-skype-for-business-clients"></a><span data-ttu-id="4596d-103">Usare le opzioni della riga di comando di configurazione con i client Skype for business</span><span class="sxs-lookup"><span data-stu-id="4596d-103">Use Setup command-line options with Skype for Business clients</span></span>
 
<span data-ttu-id="4596d-104">**Riepilogo:** Informazioni sulle operazioni della riga di comando Setup. exe in configurazione di Office.</span><span class="sxs-lookup"><span data-stu-id="4596d-104">**Summary:** Learn about Setup.exe command line operations in Office setup.</span></span>
  
<span data-ttu-id="4596d-105">La riga di comando Setup. exe viene usata per pochissime operazioni in configurazione di Office.</span><span class="sxs-lookup"><span data-stu-id="4596d-105">The Setup.exe command line is used for very few operations in Office setup.</span></span> <span data-ttu-id="4596d-106">Invece di usare le opzioni della riga di comando per la configurazione, in genere si usa lo strumento di personalizzazione di Office e il file config. XML per la configurazione del prodotto e la personalizzazione delle funzionalità.</span><span class="sxs-lookup"><span data-stu-id="4596d-106">Instead of using the Setup command-line options, you'll typically use the Office Customization Tool and the Config.xml file for product setup and feature customization.</span></span>
  
<span data-ttu-id="4596d-107">La riga di comando di Office Setup. exe riconosce le opzioni della riga di comando descritte nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="4596d-107">The Office Setup.exe command line recognizes the command-line options described in the following table.</span></span>
  
<span data-ttu-id="4596d-108">**Opzioni della riga di comando per l'installazione di Office**</span><span class="sxs-lookup"><span data-stu-id="4596d-108">**Office Setup Command-Line Options**</span></span>

|<span data-ttu-id="4596d-109">**Opzione della riga di comando Setup**</span><span class="sxs-lookup"><span data-stu-id="4596d-109">**Setup Command-Line Option**</span></span>|<span data-ttu-id="4596d-110">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="4596d-110">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="4596d-111">/admin</span><span class="sxs-lookup"><span data-stu-id="4596d-111">/admin</span></span>  <br/> |<span data-ttu-id="4596d-112">Esegue lo strumento di personalizzazione di Office per creare un file di personalizzazione della configurazione (file msp).</span><span class="sxs-lookup"><span data-stu-id="4596d-112">Runs the Office Customization Tool to create a Setup customization file (.msp file).</span></span>  <br/> |
|<span data-ttu-id="4596d-113">/adminfile [percorso]</span><span class="sxs-lookup"><span data-stu-id="4596d-113">/adminfile [path]</span></span>  <br/> |<span data-ttu-id="4596d-114">Applica il file di personalizzazione della configurazione specificato all'installazione.</span><span class="sxs-lookup"><span data-stu-id="4596d-114">Applies the specified Setup customization file to the installation.</span></span> <span data-ttu-id="4596d-115">È possibile specificare un percorso di un file di personalizzazione specifico (file msp) o nella cartella in cui vengono archiviati i file di personalizzazione.</span><span class="sxs-lookup"><span data-stu-id="4596d-115">You can specify a path of a specific customization file (.msp file) or to the folder where you store customization files.</span></span>  <br/> |
|<span data-ttu-id="4596d-116">/config [percorso]</span><span class="sxs-lookup"><span data-stu-id="4596d-116">/config [path]</span></span>  <br/> |<span data-ttu-id="4596d-117">Specifica il file config. XML usato dalla configurazione durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="4596d-117">Specifies the Config.xml file that Setup uses during the installation.</span></span> <span data-ttu-id="4596d-118">Usare l'opzione/config per specificare il file config. XML personalizzato per le installazioni di Skype for business, ad esempio:`/config \\server\share\Skype15\Skype.WW\Config.xml`</span><span class="sxs-lookup"><span data-stu-id="4596d-118">Use the /config option to specify the Config.xml file you customized for Skype for Business installations, for example:  `/config \\server\share\Skype15\Skype.WW\Config.xml`</span></span> <br/> |
|<span data-ttu-id="4596d-119">/Modify Skype</span><span class="sxs-lookup"><span data-stu-id="4596d-119">/modify Skype</span></span>  <br/> |<span data-ttu-id="4596d-120">Usato con un file config. xml modificato per eseguire la configurazione in modalità manutenzione e apportare modifiche a un'installazione di Office esistente.</span><span class="sxs-lookup"><span data-stu-id="4596d-120">Used with a modified Config.xml file to run Setup in maintenance mode and make changes to an existing Office installation.</span></span> <span data-ttu-id="4596d-121">Ad esempio, puoi usare l'opzione/MODIFY per aggiungere o rimuovere le funzionalità di Skype for business.</span><span class="sxs-lookup"><span data-stu-id="4596d-121">For example, you can use the /modify option to add or remove Skype for Business features.</span></span>  <br/> |
|<span data-ttu-id="4596d-122">/Repair Skype</span><span class="sxs-lookup"><span data-stu-id="4596d-122">/repair Skype</span></span>  <br/> |<span data-ttu-id="4596d-123">Esegue la configurazione dal computer dell'utente per ripristinare Skype for business.</span><span class="sxs-lookup"><span data-stu-id="4596d-123">Runs Setup from the user's computer to repair Skype for Business.</span></span>  <br/> |
|<span data-ttu-id="4596d-124">/Uninstall Skype</span><span class="sxs-lookup"><span data-stu-id="4596d-124">/uninstall Skype</span></span>  <br/> |<span data-ttu-id="4596d-125">Esegue il programma di installazione per rimuovere Skype for business dal computer dell'utente.</span><span class="sxs-lookup"><span data-stu-id="4596d-125">Runs Setup to remove Skype for Business from the user's computer.</span></span>  <br/> |
   


