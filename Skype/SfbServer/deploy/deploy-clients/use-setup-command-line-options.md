---
title: Utilizzare le opzioni della riga di comando del programma di installazione con i client Skype for business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
description: 'Riepilogo: informazioni su Setup.exe operazioni della riga di comando nel programma di installazione di Office.'
ms.openlocfilehash: 042ba2bdea6228f7c8a726c0bdb2ca5c3233d5f4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49837206"
---
# <a name="use-setup-command-line-options-with-skype-for-business-clients"></a><span data-ttu-id="77cc3-103">Utilizzare le opzioni della riga di comando del programma di installazione con i client Skype for business</span><span class="sxs-lookup"><span data-stu-id="77cc3-103">Use Setup command-line options with Skype for Business clients</span></span>
 
<span data-ttu-id="77cc3-104">**Riepilogo:** Informazioni su Setup.exe operazioni della riga di comando nel programma di installazione di Office.</span><span class="sxs-lookup"><span data-stu-id="77cc3-104">**Summary:** Learn about Setup.exe command line operations in Office setup.</span></span>
  
<span data-ttu-id="77cc3-105">La riga di comando di Setup.exe consente di eseguire un numero limitato di operazioni di configurazione di Office.</span><span class="sxs-lookup"><span data-stu-id="77cc3-105">The Setup.exe command line is used for very few operations in Office setup.</span></span> <span data-ttu-id="77cc3-106">Invece di utilizzare le opzioni della riga di comando del programma di installazione, in genere viene utilizzato lo strumento di personalizzazione di Office e il file di Config.xml per l'installazione del prodotto e la personalizzazione delle funzionalità.</span><span class="sxs-lookup"><span data-stu-id="77cc3-106">Instead of using the Setup command-line options, you'll typically use the Office Customization Tool and the Config.xml file for product setup and feature customization.</span></span>
  
<span data-ttu-id="77cc3-107">La riga di comando di Setup.exe di Office riconosce le opzioni descritte nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="77cc3-107">The Office Setup.exe command line recognizes the command-line options described in the following table.</span></span>
  
<span data-ttu-id="77cc3-108">**Opzioni della riga di comando del programma di installazione di Office**</span><span class="sxs-lookup"><span data-stu-id="77cc3-108">**Office Setup Command-Line Options**</span></span>

|<span data-ttu-id="77cc3-109">**Opzione della riga di comando**</span><span class="sxs-lookup"><span data-stu-id="77cc3-109">**Setup Command-Line Option**</span></span>|<span data-ttu-id="77cc3-110">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="77cc3-110">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="77cc3-111">/admin</span><span class="sxs-lookup"><span data-stu-id="77cc3-111">/admin</span></span>  <br/> |<span data-ttu-id="77cc3-112">Esegue lo Strumento di personalizzazione di Office per creare un file di personalizzazione della configurazione (file con estensione msp).</span><span class="sxs-lookup"><span data-stu-id="77cc3-112">Runs the Office Customization Tool to create a Setup customization file (.msp file).</span></span>  <br/> |
|<span data-ttu-id="77cc3-113">/adminfile [percorso]</span><span class="sxs-lookup"><span data-stu-id="77cc3-113">/adminfile [path]</span></span>  <br/> |<span data-ttu-id="77cc3-p102">Applica all'installazione il file di personalizzazione dell'installazione specificato. È possibile specificare il percorso di un determinato file di personalizzazione dell'installazione (msp) o della cartella in cui sono archiviati i file di personalizzazione.</span><span class="sxs-lookup"><span data-stu-id="77cc3-p102">Applies the specified Setup customization file to the installation. You can specify a path of a specific customization file (.msp file) or to the folder where you store customization files.</span></span>  <br/> |
|<span data-ttu-id="77cc3-116">/config [percorso]</span><span class="sxs-lookup"><span data-stu-id="77cc3-116">/config [path]</span></span>  <br/> |<span data-ttu-id="77cc3-117">Specifica il file Config.xml utilizzato durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="77cc3-117">Specifies the Config.xml file that Setup uses during the installation.</span></span> <span data-ttu-id="77cc3-118">Utilizzare l'opzione/config per specificare il file Config.xml personalizzato per le installazioni di Skype for business, ad esempio:  `/config \\server\share\Skype15\Skype.WW\Config.xml`</span><span class="sxs-lookup"><span data-stu-id="77cc3-118">Use the /config option to specify the Config.xml file you customized for Skype for Business installations, for example:  `/config \\server\share\Skype15\Skype.WW\Config.xml`</span></span> <br/> |
|<span data-ttu-id="77cc3-119">/Modify Skype</span><span class="sxs-lookup"><span data-stu-id="77cc3-119">/modify Skype</span></span>  <br/> |<span data-ttu-id="77cc3-120">Utilizzato con un file Config.xml modificato per eseguire l'installazione in modalità manutenzione e apportare modifiche a un'installazione esistente di Office.</span><span class="sxs-lookup"><span data-stu-id="77cc3-120">Used with a modified Config.xml file to run Setup in maintenance mode and make changes to an existing Office installation.</span></span> <span data-ttu-id="77cc3-121">Ad esempio, è possibile utilizzare l'opzione/MODIFY per aggiungere o rimuovere le caratteristiche di Skype for business.</span><span class="sxs-lookup"><span data-stu-id="77cc3-121">For example, you can use the /modify option to add or remove Skype for Business features.</span></span>  <br/> |
|<span data-ttu-id="77cc3-122">/Repair Skype</span><span class="sxs-lookup"><span data-stu-id="77cc3-122">/repair Skype</span></span>  <br/> |<span data-ttu-id="77cc3-123">Esegue il programma di installazione dal computer dell'utente per ripristinare Skype for business.</span><span class="sxs-lookup"><span data-stu-id="77cc3-123">Runs Setup from the user's computer to repair Skype for Business.</span></span>  <br/> |
|<span data-ttu-id="77cc3-124">/Uninstall Skype</span><span class="sxs-lookup"><span data-stu-id="77cc3-124">/uninstall Skype</span></span>  <br/> |<span data-ttu-id="77cc3-125">Esegue il programma di installazione per rimuovere Skype for business dal computer dell'utente.</span><span class="sxs-lookup"><span data-stu-id="77cc3-125">Runs Setup to remove Skype for Business from the user's computer.</span></span>  <br/> |
   


