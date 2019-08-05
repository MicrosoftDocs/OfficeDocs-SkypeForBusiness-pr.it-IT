---
title: Distribuire client per Skype for Business Server
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
description: 'Riepilogo: Panoramica dei metodi di installazione client aziendali per Skype for business.'
ms.openlocfilehash: df9ac5356c05001df09168ca619ffc200b35ea4f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36189578"
---
# <a name="deploy-clients-for-skype-for-business-server"></a><span data-ttu-id="b9072-103">Distribuire client per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="b9072-103">Deploy clients for Skype for Business Server</span></span>
 
<span data-ttu-id="b9072-104">**Riepilogo:** Panoramica dei metodi di installazione client Enterprise per Skype for business.</span><span class="sxs-lookup"><span data-stu-id="b9072-104">**Summary:** Overview of enterprise client installation methods for Skype for Business.</span></span>
  
<span data-ttu-id="b9072-105">La modalità di distribuzione di Skype for business agli utenti dipende dal fatto che sia stato acquistato Skype for business come parte di un piano di Office 365 oppure che sia stata acquistata una versione con contratto multilicenza di Skype for business.</span><span class="sxs-lookup"><span data-stu-id="b9072-105">How you deploy Skype for Business to your users depends on whether you purchased Skype for Business as part of an Office 365 plan or you purchased a volume licensed version of Skype for Business.</span></span> 
  
- <span data-ttu-id="b9072-106">**Office 365** Se si ha un piano di Office 365 che include Skype for business, la tecnologia di installazione usata viene chiamata a portata di clic.</span><span class="sxs-lookup"><span data-stu-id="b9072-106">**Office 365** If you have an Office 365 plan that includes Skype for Business, the installation technology that's used is called Click-to-Run.</span></span> <span data-ttu-id="b9072-107">Con Office 365 puoi consentire agli utenti di installare Skype for business dal portale di Office 365.</span><span class="sxs-lookup"><span data-stu-id="b9072-107">With Office 365, you can let your users install Skype for Business for themselves from the Office 365 portal.</span></span> <span data-ttu-id="b9072-108">In alternativa, è possibile distribuire Skype for business agli utenti scaricando il software nella rete locale e usando gli strumenti di distribuzione del software esistenti, ad esempio con Microsoft System Center Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="b9072-108">Or, you can deploy Skype for Business to your users by downloading the software to your local network and then using your existing software deployment tools, such as with Microsoft System Center Configuration Manager.</span></span> <span data-ttu-id="b9072-109">Per informazioni sull'installazione di Skype for business incluso in Office 365, vedere [distribuire il client Skype for business in office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span><span class="sxs-lookup"><span data-stu-id="b9072-109">For installation information about Skype for Business that comes with Office 365, see [Deploy the Skype for Business client in Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span></span>
    
- <span data-ttu-id="b9072-110">**Contratti multilicenza** Se si ha una versione con contratto multilicenza del client Skype for business 2015 o 2016, la tecnologia di installazione usata è Windows Installer (MSI).</span><span class="sxs-lookup"><span data-stu-id="b9072-110">**Volume licensed** If you have a volume licensed version of the Skype for Business 2015 or 2016 client, the installation technology that's used is Windows Installer (MSI).</span></span> <span data-ttu-id="b9072-111">Un pacchetto di installazione basato su Windows Installer è costituito da più file MSI.</span><span class="sxs-lookup"><span data-stu-id="b9072-111">A Windows Installer-based installation package consists of multiple MSI files.</span></span> <span data-ttu-id="b9072-112">Un pacchetto MSI di base indipendente dalla lingua viene combinato con uno o più pacchetti specifici della lingua per creare un prodotto completo.</span><span class="sxs-lookup"><span data-stu-id="b9072-112">A language-neutral core MSI package is combined with one or more language-specific packages to make a complete product.</span></span> <span data-ttu-id="b9072-113">La configurazione assembla i singoli pacchetti ed esegue le attività di personalizzazione e manutenzione durante e dopo l'installazione di Office nei computer degli utenti.</span><span class="sxs-lookup"><span data-stu-id="b9072-113">Setup assembles the individual packages and performs customization and maintenance tasks during and after installation of Office on users' computers.</span></span> <span data-ttu-id="b9072-114">Il client Skype for business 2019 usa programmi di installazione a portata di clic.</span><span class="sxs-lookup"><span data-stu-id="b9072-114">The Skype for Business 2019 client uses Click-to-Run installers.</span></span>
    
<span data-ttu-id="b9072-115">Gli argomenti in questa sezione descrivono come usare e personalizzare Windows Installer per distribuire il client Skype for business agli utenti tramite le normali procedure.</span><span class="sxs-lookup"><span data-stu-id="b9072-115">The topics in this section describe how to use and customize the Windows Installer to deploy the Skype for Business client to your users through your normal procedures.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b9072-116">Il componente aggiuntivo riunione Skype per Microsoft Office, che supporta la gestione delle riunioni dall'interno del client di messaggistica e collaborazione di Outlook, viene installato automaticamente con i client Skype for business.</span><span class="sxs-lookup"><span data-stu-id="b9072-116">The Skype Meeting Add-in for Microsoft Office, which supports meeting management from within the Outlook messaging and collaboration client, installs automatically with Skype for Business clients.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="b9072-117">Il programma di installazione di Office 365 non disinstalla versioni precedenti di Lync.</span><span class="sxs-lookup"><span data-stu-id="b9072-117">The Office 365 setup program does not uninstall previous versions of Lync.</span></span> <span data-ttu-id="b9072-118">Il client Skype for business installa affiancato ad altri client Lync.</span><span class="sxs-lookup"><span data-stu-id="b9072-118">The Skype for Business client installs side-by-side with other Lync clients.</span></span> 
  
## <a name="installing-windows-clients"></a><span data-ttu-id="b9072-119">Installazione di client Windows</span><span class="sxs-lookup"><span data-stu-id="b9072-119">Installing Windows clients</span></span>

- [<span data-ttu-id="b9072-120">Personalizzare l'installazione del client Windows in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="b9072-120">Customize Windows client installation in Skype for Business Server</span></span>](customize-windows-client-installation.md)
    
- [<span data-ttu-id="b9072-121">Configurare l'esperienza client con Skype for Business</span><span class="sxs-lookup"><span data-stu-id="b9072-121">Configure the client experience with Skype for Business</span></span>](configure-the-client-experience.md)
    
- [<span data-ttu-id="b9072-122">Configurare l'elenco contatti intelligenti in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="b9072-122">Configure Smart contacts list in Skype for Business Server</span></span>](configure-smart-contacts-list.md)
    
## <a name="installing-device-clients"></a><span data-ttu-id="b9072-123">Installazione dei client di dispositivi</span><span class="sxs-lookup"><span data-stu-id="b9072-123">Installing device clients</span></span>

- [<span data-ttu-id="b9072-124">Installare e testare Skype for business per Windows Phone</span><span class="sxs-lookup"><span data-stu-id="b9072-124">Install and test Skype for Business for Windows Phone</span></span>](windows-phone.md)
    
- [<span data-ttu-id="b9072-125">Installare e testare Skype for business per iOS</span><span class="sxs-lookup"><span data-stu-id="b9072-125">Install and test Skype for Business for iOS</span></span>](ios.md)
    
    
- [<span data-ttu-id="b9072-126">Distribuire il plug-in di Lync VDI con Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="b9072-126">Deploy the Lync VDI plug-in with Skype for Business Server</span></span>](deploy-the-lync-vdi-plug-in.md)
    
- [<span data-ttu-id="b9072-127">Distribuire client scaricabili Web in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="b9072-127">Deploy Web downloadable clients in Skype for Business Server</span></span>](deploy-web-downloadable-clients.md)
    
- [<span data-ttu-id="b9072-128">Personalizzare l'esperienza del client Mac in Skype for business</span><span class="sxs-lookup"><span data-stu-id="b9072-128">Customize the Mac client experience in Skype for Business</span></span>](customize-the-mac-client-experience.md)
    
## <a name="see-also"></a><span data-ttu-id="b9072-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b9072-129">See also</span></span>

[<span data-ttu-id="b9072-130">Distribuire il client Skype for business in Office 365</span><span class="sxs-lookup"><span data-stu-id="b9072-130">Deploy the Skype for Business client in Office 365</span></span>](../../../SfbOnline/set-up-skype-for-business-online/deploy-the-skype-for-business-client-in-office-365.md)
