---
title: Usare lo strumento di personalizzazione di Office (ott) in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26647cb6-ba84-4ba7-8b6f-2cf86818e530
description: 'Riepilogo: come usare lo strumento di personalizzazione di Office con il client Skype for business.'
ms.openlocfilehash: b5c66fee4f6c879c8ded2897b64e63654dd950be
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001596"
---
# <a name="use-the-office-customization-tool-oct-in-skype-for-business-server"></a><span data-ttu-id="28611-103">Usare lo strumento di personalizzazione di Office (ott) in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="28611-103">Use the Office Customization Tool (OCT) in Skype for Business Server</span></span>
 
<span data-ttu-id="28611-104">**Riepilogo:** Come usare lo strumento di personalizzazione di Office con il client Skype for business.</span><span class="sxs-lookup"><span data-stu-id="28611-104">**Summary:** How to use the Office Customization Tool with the Skype for Business client.</span></span>
  
<span data-ttu-id="28611-105">Lo strumento di personalizzazione di Office (ott) fa parte del programma di installazione ed è lo strumento consigliato per molte personalizzazioni.</span><span class="sxs-lookup"><span data-stu-id="28611-105">The Office Customization Tool (OCT) is part of the Setup program and is the recommended tool for many customizations.</span></span> <span data-ttu-id="28611-106">Usando lo strumento di personalizzazione di Office, è possibile personalizzare l'ufficio e salvare le personalizzazioni in un file msp di personalizzazione della configurazione.</span><span class="sxs-lookup"><span data-stu-id="28611-106">By using the OCT, you customize Office and save your customizations in a Setup customization .msp file.</span></span> <span data-ttu-id="28611-107">Si inserisce il file nella cartella Updates nel punto di installazione della rete.</span><span class="sxs-lookup"><span data-stu-id="28611-107">You place the file in the Updates folder on the network installation point.</span></span> <span data-ttu-id="28611-108">Durante l'installazione di Office, la configurazione Cerca un file di personalizzazione della configurazione nella cartella Updates e applica le personalizzazioni.</span><span class="sxs-lookup"><span data-stu-id="28611-108">When you install Office, Setup looks for a Setup customization file in the Updates folder and applies the customizations.</span></span> <span data-ttu-id="28611-109">La cartella Updates può essere usata solo per distribuire gli aggiornamenti software durante un'installazione iniziale di Office.</span><span class="sxs-lookup"><span data-stu-id="28611-109">The Updates folder can be used only to deploy software updates during an initial installation of Office.</span></span>
  
<span data-ttu-id="28611-110">Lo strumento di personalizzazione di ottobre fa parte del programma di installazione e viene usato solo per le versioni con contratto multilicenza del prodotto.</span><span class="sxs-lookup"><span data-stu-id="28611-110">The OCT is part of setup and it is only used for volume licensed versions of the product.</span></span> <span data-ttu-id="28611-111">Si esegue lo strumento di personalizzazione `setup.exe /admin` di Office digitando la riga di comando dalla radice del punto di installazione di rete che contiene i file di origine.</span><span class="sxs-lookup"><span data-stu-id="28611-111">You run the OCT by typing  `setup.exe /admin` at the command line from the root of the network installation point that contains the Office source files.</span></span> <span data-ttu-id="28611-112">Ad esempio, usare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="28611-112">For example, use the following:</span></span>
  
 ```console
\\server\share\Office15\setup.exe /admin
```
  
<span data-ttu-id="28611-113">Gli amministratori usano lo strumento di personalizzazione di ottobre per creare un file msp di personalizzazione della configurazione e possono personalizzare le aree seguenti:</span><span class="sxs-lookup"><span data-stu-id="28611-113">Administrators use the OCT to create a setup customization .msp file and can customize the following areas:</span></span>
  
- <span data-ttu-id="28611-114">**Configurazione** Usato per specificare il percorso di installazione predefinito nel client e il nome dell'organizzazione predefinito, altre origini di installazione di rete, codice Product Key, contratto di licenza con l'utente finale, livello di visualizzazione, versioni precedenti di Office da rimuovere, programmi personalizzati da eseguire durante l'installazione, le impostazioni di sicurezza e le proprietà di configurazione.</span><span class="sxs-lookup"><span data-stu-id="28611-114">**Setup** Used to specify default installation location on the client and default organization name, additional network installation sources, product key, end-user license agreement, display level, earlier versions of Office to remove, custom programs to run during installation, security settings, and Setup properties.</span></span>
    
- <span data-ttu-id="28611-115">**Caratteristiche** Consente di configurare le impostazioni utente e di personalizzare la modalità di installazione delle funzionalità di Office.</span><span class="sxs-lookup"><span data-stu-id="28611-115">**Features** Used to configure user settings and to customize how Office features are installed.</span></span> <span data-ttu-id="28611-116">Gli amministratori possono usare lo strumento di personalizzazione di Office per specificare i valori predefiniti iniziali delle impostazioni dell'applicazione per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="28611-116">Administrators can use the OCT to specify initial default values of Office application settings for users.</span></span> <span data-ttu-id="28611-117">Gli utenti possono modificare la maggior parte delle impostazioni dopo l'installazione.</span><span class="sxs-lookup"><span data-stu-id="28611-117">Users can modify most of the settings after the installation.</span></span>
    
- <span data-ttu-id="28611-118">**Contenuto aggiuntivo** Consente di aggiungere o rimuovere file, aggiungere o rimuovere voci del registro di sistema e configurare i tasti di scelta rapida.</span><span class="sxs-lookup"><span data-stu-id="28611-118">**Additional content** Used to add or remove files, add or remove registry entries, and configure shortcuts.</span></span>
    
- <span data-ttu-id="28611-119">**Outlook** Usato per personalizzare il profilo di Outlook predefinito di un utente, specificare le impostazioni di Exchange, aggiungere account, rimuovere gli account ed esportare le impostazioni e specificare i gruppi di invio/ricezione.</span><span class="sxs-lookup"><span data-stu-id="28611-119">**Outlook** Used to customize a user's default Outlook profile, specify Exchange settings, add accounts, remove accounts and export settings, and specify Send\Receive groups.</span></span>
    
<span data-ttu-id="28611-120">Per informazioni su questo strumento, vedere [usare lo strumento di personalizzazione di Office per personalizzare la 2013](https://docs.microsoft.com/previous-versions/office/office-2013-resource-kit/cc179132(v=office.15)).</span><span class="sxs-lookup"><span data-stu-id="28611-120">For information about the OCT, see [Use the OCT to customize Office 2013](https://docs.microsoft.com/previous-versions/office/office-2013-resource-kit/cc179132(v=office.15)).</span></span> <span data-ttu-id="28611-121">Tieni presente che queste informazioni si applicano anche alle versioni successive di Office.</span><span class="sxs-lookup"><span data-stu-id="28611-121">Note that this information also applies to later versions of Office.</span></span>
  

