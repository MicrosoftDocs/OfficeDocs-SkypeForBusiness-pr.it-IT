---
title: Usare lo Strumento di personalizzazione di Office in Skype for Business Server
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
ms.assetid: 26647cb6-ba84-4ba7-8b6f-2cf86818e530
description: 'Riepilogo: come usare lo Strumento di personalizzazione di Office con il client Skype for Business.'
ms.openlocfilehash: 32cd7951690ce5b1e38c20d83c8f53a9c48cd19c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100452"
---
# <a name="use-the-office-customization-tool-oct-in-skype-for-business-server"></a><span data-ttu-id="14342-103">Usare lo Strumento di personalizzazione di Office in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="14342-103">Use the Office Customization Tool (OCT) in Skype for Business Server</span></span>
 
<span data-ttu-id="14342-104">**Riepilogo:** Come usare lo Strumento di personalizzazione di Office con il client Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="14342-104">**Summary:** How to use the Office Customization Tool with the Skype for Business client.</span></span>
  
<span data-ttu-id="14342-105">Lo Strumento di personalizzazione di Office fa parte del programma di installazione ed è lo strumento consigliato per molte personalizzazioni.</span><span class="sxs-lookup"><span data-stu-id="14342-105">The Office Customization Tool (OCT) is part of the Setup program and is the recommended tool for many customizations.</span></span> <span data-ttu-id="14342-106">Tramite questo strumento, è possibile personalizzare Office e salvare le personalizzazioni in un file di configurazione dell'installazione con estensione msp.</span><span class="sxs-lookup"><span data-stu-id="14342-106">By using the OCT, you customize Office and save your customizations in a Setup customization .msp file.</span></span> <span data-ttu-id="14342-107">Il file viene inserito nella cartella Aggiornamenti nella posizione di installazione dalla rete.</span><span class="sxs-lookup"><span data-stu-id="14342-107">You place the file in the Updates folder on the network installation point.</span></span> <span data-ttu-id="14342-108">Quando si installa Office, il programma di installazione cerca un file di configurazione dell'installazione nella cartella Aggiornamenti e applica le personalizzazioni.</span><span class="sxs-lookup"><span data-stu-id="14342-108">When you install Office, Setup looks for a Setup customization file in the Updates folder and applies the customizations.</span></span> <span data-ttu-id="14342-109">La cartella Updates può essere utilizzata solo per distribuire gli aggiornamenti software durante un'installazione iniziale di Office.</span><span class="sxs-lookup"><span data-stu-id="14342-109">The Updates folder can be used only to deploy software updates during an initial installation of Office.</span></span>
  
<span data-ttu-id="14342-110">Lo Strumento di personalizzazione di Office fa parte dell'installazione e viene utilizzato solo per le versioni con contratto multilicenza del prodotto.</span><span class="sxs-lookup"><span data-stu-id="14342-110">The OCT is part of setup and it is only used for volume licensed versions of the product.</span></span> <span data-ttu-id="14342-111">Eseguire lo Strumento di personalizzazione di Office digitando nella riga di comando dalla radice del punto di installazione di rete  `setup.exe /admin` contenente i file di origine di Office.</span><span class="sxs-lookup"><span data-stu-id="14342-111">You run the OCT by typing  `setup.exe /admin` at the command line from the root of the network installation point that contains the Office source files.</span></span> <span data-ttu-id="14342-112">Ad esempio, utilizzare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="14342-112">For example, use the following:</span></span>
  
 ```console
\\server\share\Office15\setup.exe /admin
```
  
<span data-ttu-id="14342-113">Gli amministratori utilizzano lo Strumento di personalizzazione di Office per creare un file msp di personalizzazione dell'installazione e possono personalizzare le aree seguenti:</span><span class="sxs-lookup"><span data-stu-id="14342-113">Administrators use the OCT to create a setup customization .msp file and can customize the following areas:</span></span>
  
- <span data-ttu-id="14342-114">**Installazione** Utilizzato per specificare il percorso di installazione predefinito nel client e nel nome dell'organizzazione predefinito, origini di installazione di rete aggiuntive, codice Product Key, contratto di licenza con l'utente finale, livello di visualizzazione, versioni precedenti di Office da rimuovere, programmi personalizzati da eseguire durante l'installazione, impostazioni di sicurezza e proprietà del programma di installazione.</span><span class="sxs-lookup"><span data-stu-id="14342-114">**Setup** Used to specify default installation location on the client and default organization name, additional network installation sources, product key, end-user license agreement, display level, earlier versions of Office to remove, custom programs to run during installation, security settings, and Setup properties.</span></span>
    
- <span data-ttu-id="14342-115">**Funzionalità** Utilizzato per configurare le impostazioni utente e personalizzare la modalità di installazione delle caratteristiche di Office.</span><span class="sxs-lookup"><span data-stu-id="14342-115">**Features** Used to configure user settings and to customize how Office features are installed.</span></span> <span data-ttu-id="14342-116">Gli amministratori possono utilizzare lo Strumento di personalizzazione di Office per specificare valori predefiniti iniziali delle impostazioni delle applicazioni Office per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="14342-116">Administrators can use the OCT to specify initial default values of Office application settings for users.</span></span> <span data-ttu-id="14342-117">Gli utenti possono modificare la maggior parte delle impostazioni dopo l'installazione.</span><span class="sxs-lookup"><span data-stu-id="14342-117">Users can modify most of the settings after the installation.</span></span>
    
- <span data-ttu-id="14342-118">**Contenuto aggiuntivo** Usato per aggiungere o rimuovere file, aggiungere o rimuovere voci del Registro di sistema e configurare collegamenti.</span><span class="sxs-lookup"><span data-stu-id="14342-118">**Additional content** Used to add or remove files, add or remove registry entries, and configure shortcuts.</span></span>
    
- <span data-ttu-id="14342-119">**Outlook** Utilizzato per personalizzare il profilo outlook predefinito di un utente, specificare le impostazioni di Exchange, aggiungere account, rimuovere account ed esportare le impostazioni e specificare Send\Receive groups.</span><span class="sxs-lookup"><span data-stu-id="14342-119">**Outlook** Used to customize a user's default Outlook profile, specify Exchange settings, add accounts, remove accounts and export settings, and specify Send\Receive groups.</span></span>
    
<span data-ttu-id="14342-120">Per informazioni sullo Strumento di personalizzazione di Office, vedere [Utilizzare lo Strumento di personalizzazione di Office per personalizzare Office 2013.](/previous-versions/office/office-2013-resource-kit/cc179132(v=office.15))</span><span class="sxs-lookup"><span data-stu-id="14342-120">For information about the OCT, see [Use the OCT to customize Office 2013](/previous-versions/office/office-2013-resource-kit/cc179132(v=office.15)).</span></span> <span data-ttu-id="14342-121">Si noti che queste informazioni si applicano anche alle versioni successive di Office.</span><span class="sxs-lookup"><span data-stu-id="14342-121">Note that this information also applies to later versions of Office.</span></span>
