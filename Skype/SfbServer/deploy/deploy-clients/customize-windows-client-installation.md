---
title: Personalizzare l'installazione del client Windows in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5c1a85f1-5ebb-48fb-acb7-3bf46decbf80
description: 'Riepilogo: Panoramica dei metodi di installazione e degli strumenti per Skype for business.'
ms.openlocfilehash: 16c460d8fbbafd98a980c69bc0cd7638108ea164
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234436"
---
# <a name="customize-windows-client-installation-in-skype-for-business-server"></a><span data-ttu-id="3d920-103">Personalizzare l'installazione del client Windows in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="3d920-103">Customize Windows client installation in Skype for Business Server</span></span>
 
<span data-ttu-id="3d920-104">**Riepilogo:** Panoramica dei metodi di installazione e degli strumenti per Skype for business.</span><span class="sxs-lookup"><span data-stu-id="3d920-104">**Summary:** Overview of installation methods and tools for Skype for Business.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3d920-105">Per informazioni sull'installazione di Skype for business incluso in Office 365, vedere [distribuire il client Skype for business in office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span><span class="sxs-lookup"><span data-stu-id="3d920-105">For installation information about Skype for Business that comes with Office 365, see [Deploy the Skype for Business client in Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span></span> 
  
<span data-ttu-id="3d920-106">Gli amministratori aziendali possono personalizzare l'installazione basata su Windows Installer (con estensione msi) di versioni con contratto multilicenza di Skype for business usando i metodi descritti in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="3d920-106">Enterprise administrators can customize the Windows Installer-based (.msi) installation of volume licensed versions of Skype for Business by using the methods discussed in this section.</span></span> <span data-ttu-id="3d920-107">Dato che nessun singolo strumento offre tutte le opzioni di personalizzazione, è probabile che usi una combinazione di questi metodi nella distribuzione di Skype for business.</span><span class="sxs-lookup"><span data-stu-id="3d920-107">Because no single tool provides all customization options, you'll likely use a combination of these methods in your Skype for Business deployment.</span></span> <span data-ttu-id="3d920-108">È possibile usare gli strumenti descritti nelle sezioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3d920-108">You might use the tools described in the following sections:</span></span>
  
- <span data-ttu-id="3d920-109">[Usare lo strumento di personalizzazione di Office in Skype for Business Server](use-the-office-customization-tool-oct.md) per personalizzare le opzioni di configurazione e le funzionalità per Skype for business e altre applicazioni di Office.</span><span class="sxs-lookup"><span data-stu-id="3d920-109">[Use the Office Customization Tool (OCT) in Skype for Business Server](use-the-office-customization-tool-oct.md) to customize setup options and features for Skype for Business and other Office programs.</span></span>
    
- <span data-ttu-id="3d920-110">[USA config. XML per eseguire attività di installazione in Skype for Business Server](use-config-xml-to-perform-installation-tasks.md) per specificare il percorso del punto di installazione di rete ed eseguire l'installazione invisibile all'utente.</span><span class="sxs-lookup"><span data-stu-id="3d920-110">[Use Config.xml to perform installation tasks in Skype for Business Server](use-config-xml-to-perform-installation-tasks.md) to specify the path of the network installation point and perform silent installation.</span></span>
    
- <span data-ttu-id="3d920-111">[Usare le opzioni della riga di comando di configurazione in Skype for Business Server](use-setup-command-line-options.md) per specificare il file config. XML da usare durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="3d920-111">[Use Setup command-line options in Skype for Business Server](use-setup-command-line-options.md) to specify the Config.xml file to use during installation.</span></span>
    
- <span data-ttu-id="3d920-112">[Configurare i criteri di avvio del client in Skype for Business Server](configure-client-bootstrapping-policies.md) usando lo snap-in MMC Editor oggetti Criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="3d920-112">[Configure client bootstrapping policies in Skype for Business Server](configure-client-bootstrapping-policies.md) by using the Group Policy Object Editor MMC snap-in.</span></span>
    
<span data-ttu-id="3d920-113">Ci saranno probabilmente altre opzioni che vorrai configurare mentre Distribuisci la famiglia di prodotti Office.</span><span class="sxs-lookup"><span data-stu-id="3d920-113">There will probably be other options you'll want to configure as you deploy the Office suite of products.</span></span> <span data-ttu-id="3d920-114">Gli argomenti di questa sezione forniscono una panoramica di questi strumenti di personalizzazione e discutono le considerazioni specifiche di Skype for business.</span><span class="sxs-lookup"><span data-stu-id="3d920-114">The topics in this section give an overview of these customization tools and discuss considerations specific to Skype for Business.</span></span> <span data-ttu-id="3d920-115">Sono inclusi collegamenti alla guida dettagliata di Office per ogni strumento.</span><span class="sxs-lookup"><span data-stu-id="3d920-115">Included are links to detailed Office help for each tool.</span></span> 
  

