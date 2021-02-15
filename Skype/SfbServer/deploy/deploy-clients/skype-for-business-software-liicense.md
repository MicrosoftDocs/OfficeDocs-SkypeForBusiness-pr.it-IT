---
title: Licenza software Skype for Business per Skype Room System
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
f1.keywords:
- NOCSH
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78a664ba-fefc-4423-ac8f-b58e6fbc2e55
description: Leggere questo argomento per informazioni su come verificare se si dispone di un contratto multilicenza software Skype for Business.
ms.openlocfilehash: 20e04f69ba5a931bae6ac8598567165a7a6043a4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833926"
---
# <a name="skype-room-system-skype-for-business-software-license"></a><span data-ttu-id="a7bd5-103">Skype Room System: licenza software Skype for Business</span><span class="sxs-lookup"><span data-stu-id="a7bd5-103">Skype Room System: Skype for Business software license</span></span>
 
<span data-ttu-id="a7bd5-104">Leggere questo argomento per informazioni su come verificare se si dispone di un contratto multilicenza software Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="a7bd5-104">Read this topic to learn how to check whether you have a Skype for Business software volume license.</span></span> 
  
<span data-ttu-id="a7bd5-105">Skype Room System usa un client Skype for Business installato, che richiede un contratto multilicenza software.</span><span class="sxs-lookup"><span data-stu-id="a7bd5-105">Skype Room System uses an installed Skype for Business client, which requires a software volume license.</span></span> <span data-ttu-id="a7bd5-106">Prima di distribuire il primo Skype Room System, scopri lo stato dei contratti multilicenza della distribuzione usando i server di gestione delle chiavi (KMS) o più codici ad attivazione multipla (MAK).</span><span class="sxs-lookup"><span data-stu-id="a7bd5-106">Before deploying the first Skype Room System, find out the volume license state of the deployment - using Key Management Servers (KMS) or Multiple Activation Keys (MAK).</span></span>
  
## <a name="key-management-servers-kms"></a><span data-ttu-id="a7bd5-107">Server di gestione delle chiavi (KMS)</span><span class="sxs-lookup"><span data-stu-id="a7bd5-107">Key Management Servers (KMS)</span></span>

<span data-ttu-id="a7bd5-108">Se il servizio di gestione delle chiavi è sul posto e distribuirà le attivazioni dei contratti multilicenza di Skype for Business, Skype Room System attiverà automaticamente il client Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="a7bd5-108">If KMS are in place and will distribute Skype for Business Volume License activations, the Skype Room System will automatically activate the Skype for Business client.</span></span> <span data-ttu-id="a7bd5-109">Per scoprire se il servizio di gestione delle chiavi è sul posto:</span><span class="sxs-lookup"><span data-stu-id="a7bd5-109">To find out if KMS are in place:</span></span>
  
<span data-ttu-id="a7bd5-110">Da un prompt dei comandi eseguire:  `nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`</span><span class="sxs-lookup"><span data-stu-id="a7bd5-110">From a command prompt, run:  `nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`</span></span>
  
<span data-ttu-id="a7bd5-111">Per ulteriori informazioni, vedere Come individuare gli host del Servizio di gestione delle chiavi di Office e [Windows tramite DNS e rimuovere istanze non autorizzate.](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx)</span><span class="sxs-lookup"><span data-stu-id="a7bd5-111">For more information, see [How to discover Office and Windows KMS hosts via DNS and remove unauthorized instances](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx).</span></span> 
  
<span data-ttu-id="a7bd5-112">Per configurare un servizio di gestione delle chiavi, vedere [KmS activation of Office 2013](https://technet.microsoft.com/library/ee624357.aspx) and [GVLKs for KMS and Active Directory activation of Office 2013](https://technet.microsoft.com/library/dn385360.aspx)</span><span class="sxs-lookup"><span data-stu-id="a7bd5-112">To set up a KMS, see [KMS activation of Office 2013](https://technet.microsoft.com/library/ee624357.aspx) and [GVLKs for KMS and Active Directory activation of Office 2013](https://technet.microsoft.com/library/dn385360.aspx)</span></span>
  
<span data-ttu-id="a7bd5-113">Codice Product Key per contratti multilicenza generico di Office 2013 per Lync: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (questo codice fa sì che Skype Room System cerca un servizio di gestione delle chiavi nella rete).</span><span class="sxs-lookup"><span data-stu-id="a7bd5-113">Office 2013 Generic Volume License Key for Lync: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (This key causes the Skype Room System to look for a KMS on the network.)</span></span>
  
## <a name="multiple-activation-keys-mak-from-the-volume-license-service-center-vlsc"></a><span data-ttu-id="a7bd5-114">Codici "Product Key" per attivazione multipla (MAK) dal Centro servizi per contratti multilicenza</span><span class="sxs-lookup"><span data-stu-id="a7bd5-114">Multiple Activation Keys (MAK) from the Volume License Service Center (VLSC)</span></span>

<span data-ttu-id="a7bd5-115">Se il cliente usa qualsiasi altro software con contratto multilicenza, il reparto IT gestirà le attivazioni software e il Contratto multilicenza (VLA) tramite VLSC.</span><span class="sxs-lookup"><span data-stu-id="a7bd5-115">If the customer uses any other volume license software, the IT department will manage the software activations and Volume License Agreement (VLA) using the VLSC.</span></span> <span data-ttu-id="a7bd5-116">Ciò consentirà anche all'azienda di acquistare le attivazioni VL di Skype for Business, dopo di che l'azienda può ottenere un codice ad attivazione multipla per l'input nella console di amministrazione di Skype Room System.</span><span class="sxs-lookup"><span data-stu-id="a7bd5-116">This will also enable the company to purchase Skype for Business VL activations, after which the company can obtain a MAK for input in the Skype Room System Admin Console.</span></span>
  
<span data-ttu-id="a7bd5-117">Un cliente con una VLA deve conoscere le proprie credenziali VLSC, che verranno usate per amministrare il contratto e ottenere il codice ad attivazione attivazione attivazione software.</span><span class="sxs-lookup"><span data-stu-id="a7bd5-117">A customer with a VLA must know their VLSC credentials, which will be used to administer the agreement and obtain MAK.</span></span> <span data-ttu-id="a7bd5-118">In caso di dubbi, il reparto finanze del cliente dovrebbe essere in grado di confermare se il cliente ha pagato una VLA.</span><span class="sxs-lookup"><span data-stu-id="a7bd5-118">If uncertain, the customer's finance department should be able to confirm if the customer has paid for a VLA.</span></span>
  
<span data-ttu-id="a7bd5-119">Per ottenere un codice "Product Key" per attivazione programmi, accedere al Centro servizi per contratti multilicenza per visualizzare i contratti e scaricare i codici Product Key (MAK).</span><span class="sxs-lookup"><span data-stu-id="a7bd5-119">To obtain a MAK, access the Volume Licensing Service Center to view agreements and download product keys (MAK).</span></span> <span data-ttu-id="a7bd5-120">Per ulteriori informazioni, visitare il Centro servizi [per contratti multilicenza.](https://www.microsoft.com/Licensing/servicecenter/default.aspx)</span><span class="sxs-lookup"><span data-stu-id="a7bd5-120">For more information, go to the [Volume Licensing Service Center](https://www.microsoft.com/Licensing/servicecenter/default.aspx).</span></span> 
  
## <a name="mak-for-microsoft-365-or-office-365-without-vlsc-access"></a><span data-ttu-id="a7bd5-121">Codice ad attivazione attivazione attivazione programmi per Microsoft 365 o Office 365 senza accesso VLSC</span><span class="sxs-lookup"><span data-stu-id="a7bd5-121">MAK for Microsoft 365 or Office 365 without VLSC access</span></span>

<span data-ttu-id="a7bd5-122">Se il cliente non ha un contratto multilicenza, le attivazioni di Skype for Business saranno molto più difficili da gestire.</span><span class="sxs-lookup"><span data-stu-id="a7bd5-122">If the customer doesn't have a Volume License Agreement, Skype for Business activations will be much more difficult to manage.</span></span> <span data-ttu-id="a7bd5-123">Tuttavia, i clienti di Microsoft 365 e Office 365 senza accesso VLSC possono ottenere un codice "MaK" promozionale fornendo le informazioni seguenti all'OEM che vende Skype Room System:</span><span class="sxs-lookup"><span data-stu-id="a7bd5-123">However, Microsoft 365 and Office 365 customers without VLSC access can obtain a promotional MAK by providing the following information to the OEM selling the Skype Room System:</span></span>
  
- <span data-ttu-id="a7bd5-124">Nome dell'azienda</span><span class="sxs-lookup"><span data-stu-id="a7bd5-124">Company name</span></span>
    
- <span data-ttu-id="a7bd5-125">Nome del contatto di distribuzione, indirizzo di posta elettronica e numero di telefono</span><span class="sxs-lookup"><span data-stu-id="a7bd5-125">Deployment contact name, email, and phone number</span></span>
    
- <span data-ttu-id="a7bd5-126">Numero di sistemi distribuiti</span><span class="sxs-lookup"><span data-stu-id="a7bd5-126">Number of systems deployed</span></span>
    
- <span data-ttu-id="a7bd5-127">Data distribuzione</span><span class="sxs-lookup"><span data-stu-id="a7bd5-127">Deployment date</span></span>
    
- <span data-ttu-id="a7bd5-128">Se il cliente ha un responsabile dell'account tecnico Microsoft, il nome e le informazioni di contatto del TAM</span><span class="sxs-lookup"><span data-stu-id="a7bd5-128">If the customer has a Microsoft Technical Account Manager, the TAM's name and contact information</span></span>
    

