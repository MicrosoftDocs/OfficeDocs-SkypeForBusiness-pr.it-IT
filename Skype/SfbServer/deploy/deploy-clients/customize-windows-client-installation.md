---
title: Personalizzare l'installazione di Windows client in Skype for Business Server
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
ms.assetid: 5c1a85f1-5ebb-48fb-acb7-3bf46decbf80
description: 'Riepilogo: Panoramica dei metodi e degli strumenti di installazione per Skype for business.'
ms.openlocfilehash: 001224369e46978e96ee063b31fcb546ef213a05
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805716"
---
# <a name="customize-windows-client-installation-in-skype-for-business-server"></a><span data-ttu-id="19958-103">Personalizzare l'installazione di Windows client in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="19958-103">Customize Windows client installation in Skype for Business Server</span></span>
 
<span data-ttu-id="19958-104">**Riepilogo:** Panoramica dei metodi e degli strumenti di installazione per Skype for business.</span><span class="sxs-lookup"><span data-stu-id="19958-104">**Summary:** Overview of installation methods and tools for Skype for Business.</span></span>
  
> [!NOTE]
> <span data-ttu-id="19958-105">Per informazioni sull'installazione di Skype for business disponibile con Microsoft 365 e Office 365, vedere [distribuire il client Skype for business in Microsoft 365 o Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span><span class="sxs-lookup"><span data-stu-id="19958-105">For installation information about Skype for Business that comes with Microsoft 365 and Office 365, see [Deploy the Skype for Business client in Microsoft 365 or Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span></span> 
  
<span data-ttu-id="19958-106">Gli amministratori dell'organizzazione possono personalizzare l'installazione di Windows Installer (con estensione msi) di versioni con contratto multilicenza di Skype for business utilizzando i metodi illustrati in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="19958-106">Enterprise administrators can customize the Windows Installer-based (.msi) installation of volume licensed versions of Skype for Business by using the methods discussed in this section.</span></span> <span data-ttu-id="19958-107">Poiché nessun singolo strumento fornisce tutte le opzioni di personalizzazione, è probabile che si utilizzerà una combinazione di questi metodi nella distribuzione di Skype for business.</span><span class="sxs-lookup"><span data-stu-id="19958-107">Because no single tool provides all customization options, you'll likely use a combination of these methods in your Skype for Business deployment.</span></span> <span data-ttu-id="19958-108">È possibile utilizzare gli strumenti descritti nelle sezioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="19958-108">You might use the tools described in the following sections:</span></span>
  
- <span data-ttu-id="19958-109">[Utilizzare lo strumento di personalizzazione di Office in Skype for Business Server](use-the-office-customization-tool-oct.md) per personalizzare le opzioni di installazione e le funzionalità di Skype for business e di altre applicazioni di Office.</span><span class="sxs-lookup"><span data-stu-id="19958-109">[Use the Office Customization Tool (OCT) in Skype for Business Server](use-the-office-customization-tool-oct.md) to customize setup options and features for Skype for Business and other Office programs.</span></span>
    
- <span data-ttu-id="19958-110">[Utilizzare Config.xml per eseguire le attività di installazione in Skype for Business Server](use-config-xml-to-perform-installation-tasks.md) per specificare il percorso del punto di installazione di rete ed eseguire l'installazione invisibile all'utente.</span><span class="sxs-lookup"><span data-stu-id="19958-110">[Use Config.xml to perform installation tasks in Skype for Business Server](use-config-xml-to-perform-installation-tasks.md) to specify the path of the network installation point and perform silent installation.</span></span>
    
- <span data-ttu-id="19958-111">[Utilizzare le opzioni della riga di comando del programma di installazione in Skype for Business Server](use-setup-command-line-options.md) per specificare il file di Config.xml da utilizzare durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="19958-111">[Use Setup command-line options in Skype for Business Server](use-setup-command-line-options.md) to specify the Config.xml file to use during installation.</span></span>
    
- <span data-ttu-id="19958-112">[Configurare i criteri di avvio automatico dei client in Skype for Business Server](configure-client-bootstrapping-policies.md) tramite lo snap-in MMC Editor oggetti Criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="19958-112">[Configure client bootstrapping policies in Skype for Business Server](configure-client-bootstrapping-policies.md) by using the Group Policy Object Editor MMC snap-in.</span></span>
    
<span data-ttu-id="19958-113">Sono probabilmente disponibili altre opzioni che verranno configurate durante la distribuzione della famiglia di prodotti Office.</span><span class="sxs-lookup"><span data-stu-id="19958-113">There will probably be other options you'll want to configure as you deploy the Office suite of products.</span></span> <span data-ttu-id="19958-114">Negli argomenti di questa sezione viene illustrata una panoramica di questi strumenti di personalizzazione e vengono illustrate le considerazioni specifiche di Skype for business.</span><span class="sxs-lookup"><span data-stu-id="19958-114">The topics in this section give an overview of these customization tools and discuss considerations specific to Skype for Business.</span></span> <span data-ttu-id="19958-115">Sono inclusi collegamenti alle informazioni dettagliate della Guida di Office per ogni strumento.</span><span class="sxs-lookup"><span data-stu-id="19958-115">Included are links to detailed Office help for each tool.</span></span> 
  

