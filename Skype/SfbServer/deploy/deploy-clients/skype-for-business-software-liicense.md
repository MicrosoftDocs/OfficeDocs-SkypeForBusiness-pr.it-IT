---
title: Skype Room System Licenza software Skype for Business
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
ms.openlocfilehash: 40b72e39fc0edc23b4cc0d17f82ba633c2ac24af
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51113092"
---
# <a name="skype-room-system-skype-for-business-software-license"></a><span data-ttu-id="9ee76-103">Skype Room System: licenza software Skype for Business</span><span class="sxs-lookup"><span data-stu-id="9ee76-103">Skype Room System: Skype for Business software license</span></span>
 
<span data-ttu-id="9ee76-104">Leggere questo argomento per informazioni su come verificare se si dispone di un contratto multilicenza software Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="9ee76-104">Read this topic to learn how to check whether you have a Skype for Business software volume license.</span></span> 
  
<span data-ttu-id="9ee76-105">Skype Room System usa un client Skype for Business installato, che richiede un contratto multilicenza software.</span><span class="sxs-lookup"><span data-stu-id="9ee76-105">Skype Room System uses an installed Skype for Business client, which requires a software volume license.</span></span> <span data-ttu-id="9ee76-106">Prima di distribuire il primo skype room system, scopri lo stato dei contratti multilicenza della distribuzione, usando i server di gestione delle chiavi (KMS) o più chiavi di attivazione (MAK).</span><span class="sxs-lookup"><span data-stu-id="9ee76-106">Before deploying the first Skype Room System, find out the volume license state of the deployment - using Key Management Servers (KMS) or Multiple Activation Keys (MAK).</span></span>
  
## <a name="key-management-servers-kms"></a><span data-ttu-id="9ee76-107">Server di gestione delle chiavi (KMS)</span><span class="sxs-lookup"><span data-stu-id="9ee76-107">Key Management Servers (KMS)</span></span>

<span data-ttu-id="9ee76-108">Se il servizio di gestione delle chiavi è sul posto e distribuisce le attivazioni dei contratti multilicenza Skype for Business, skype room system attiverà automaticamente il client Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="9ee76-108">If KMS are in place and will distribute Skype for Business Volume License activations, the Skype Room System will automatically activate the Skype for Business client.</span></span> <span data-ttu-id="9ee76-109">Per scoprire se il servizio di gestione delle chiavi è in atto:</span><span class="sxs-lookup"><span data-stu-id="9ee76-109">To find out if KMS are in place:</span></span>
  
<span data-ttu-id="9ee76-110">Da un prompt dei comandi eseguire:  `nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`</span><span class="sxs-lookup"><span data-stu-id="9ee76-110">From a command prompt, run:  `nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`</span></span>
  
<span data-ttu-id="9ee76-111">Per ulteriori informazioni, vedere Come individuare gli host del servizio di gestione delle chiavi di Office e [Windows tramite DNS e rimuovere istanze non autorizzate.](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx)</span><span class="sxs-lookup"><span data-stu-id="9ee76-111">For more information, see [How to discover Office and Windows KMS hosts via DNS and remove unauthorized instances](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx).</span></span> 
  
<span data-ttu-id="9ee76-112">Per configurare un servizio di gestione delle chiavi, vedere Attivazione del servizio di gestione delle chiavi di [Office 2013](/previous-versions/office/office-2013-resource-kit/ee624357(v=office.15)) e GVK per il servizio di gestione delle chiavi e l'attivazione di Active Directory di [Office 2013](/DeployOffice/vlactivation/gvlks)</span><span class="sxs-lookup"><span data-stu-id="9ee76-112">To set up a KMS, see [KMS activation of Office 2013](/previous-versions/office/office-2013-resource-kit/ee624357(v=office.15)) and [GVLKs for KMS and Active Directory activation of Office 2013](/DeployOffice/vlactivation/gvlks)</span></span>
  
<span data-ttu-id="9ee76-113">Codice Product Key per contratti multilicenza generico di Office 2013 per Lync: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (Questa chiave fa sì che Skype Room System cerca un servizio di gestione delle chiavi nella rete).</span><span class="sxs-lookup"><span data-stu-id="9ee76-113">Office 2013 Generic Volume License Key for Lync: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (This key causes the Skype Room System to look for a KMS on the network.)</span></span>
  
## <a name="multiple-activation-keys-mak-from-the-volume-license-service-center-vlsc"></a><span data-ttu-id="9ee76-114">Codici ad attivazione multipla (MAK) dal Centro servizi per contratti multilicenza (VLSC)</span><span class="sxs-lookup"><span data-stu-id="9ee76-114">Multiple Activation Keys (MAK) from the Volume License Service Center (VLSC)</span></span>

<span data-ttu-id="9ee76-115">Se il cliente usa qualsiasi altro software con contratti multilicenza, il reparto IT gestirà le attivazioni software e il Contratto multilicenza (VLA) tramite VLSC.</span><span class="sxs-lookup"><span data-stu-id="9ee76-115">If the customer uses any other volume license software, the IT department will manage the software activations and Volume License Agreement (VLA) using the VLSC.</span></span> <span data-ttu-id="9ee76-116">In questo modo la società potrà anche acquistare le attivazioni VL di Skype for Business, dopo di che l'azienda potrà ottenere un codice ADK per l'input nella Console di amministrazione di Skype Room System.</span><span class="sxs-lookup"><span data-stu-id="9ee76-116">This will also enable the company to purchase Skype for Business VL activations, after which the company can obtain a MAK for input in the Skype Room System Admin Console.</span></span>
  
<span data-ttu-id="9ee76-117">Un cliente con una VLA deve conoscere le proprie credenziali VLSC, che verranno utilizzate per amministrare il contratto e ottenere il codice ADK.</span><span class="sxs-lookup"><span data-stu-id="9ee76-117">A customer with a VLA must know their VLSC credentials, which will be used to administer the agreement and obtain MAK.</span></span> <span data-ttu-id="9ee76-118">In caso di dubbi, il reparto finanziario del cliente dovrebbe essere in grado di verificare se il cliente ha pagato una VLA.</span><span class="sxs-lookup"><span data-stu-id="9ee76-118">If uncertain, the customer's finance department should be able to confirm if the customer has paid for a VLA.</span></span>
  
<span data-ttu-id="9ee76-119">Per ottenere un codice ADK, accedere al Centro servizi per contratti multilicenza per visualizzare i contratti e scaricare i codici Product Key (MAK).</span><span class="sxs-lookup"><span data-stu-id="9ee76-119">To obtain a MAK, access the Volume Licensing Service Center to view agreements and download product keys (MAK).</span></span> <span data-ttu-id="9ee76-120">Per ulteriori informazioni, passare al [Centro servizi per contratti multilicenza.](https://www.microsoft.com/Licensing/servicecenter/default.aspx)</span><span class="sxs-lookup"><span data-stu-id="9ee76-120">For more information, go to the [Volume Licensing Service Center](https://www.microsoft.com/Licensing/servicecenter/default.aspx).</span></span> 
  
## <a name="mak-for-microsoft-365-or-office-365-without-vlsc-access"></a><span data-ttu-id="9ee76-121">Codice AdO per Microsoft 365 o Office 365 senza accesso VLSC</span><span class="sxs-lookup"><span data-stu-id="9ee76-121">MAK for Microsoft 365 or Office 365 without VLSC access</span></span>

<span data-ttu-id="9ee76-122">Se il cliente non ha un contratto multilicenza, le attivazioni di Skype for Business saranno molto più difficili da gestire.</span><span class="sxs-lookup"><span data-stu-id="9ee76-122">If the customer doesn't have a Volume License Agreement, Skype for Business activations will be much more difficult to manage.</span></span> <span data-ttu-id="9ee76-123">Tuttavia, i clienti di Microsoft 365 e Office 365 senza accesso VLSC possono ottenere un codice ADK promozionale fornendo le informazioni seguenti all'OEM che vende skype room system:</span><span class="sxs-lookup"><span data-stu-id="9ee76-123">However, Microsoft 365 and Office 365 customers without VLSC access can obtain a promotional MAK by providing the following information to the OEM selling the Skype Room System:</span></span>
  
- <span data-ttu-id="9ee76-124">Nome dell'azienda</span><span class="sxs-lookup"><span data-stu-id="9ee76-124">Company name</span></span>
    
- <span data-ttu-id="9ee76-125">Nome del contatto di distribuzione, indirizzo di posta elettronica e numero di telefono</span><span class="sxs-lookup"><span data-stu-id="9ee76-125">Deployment contact name, email, and phone number</span></span>
    
- <span data-ttu-id="9ee76-126">Numero di sistemi distribuiti</span><span class="sxs-lookup"><span data-stu-id="9ee76-126">Number of systems deployed</span></span>
    
- <span data-ttu-id="9ee76-127">Data distribuzione</span><span class="sxs-lookup"><span data-stu-id="9ee76-127">Deployment date</span></span>
    
- <span data-ttu-id="9ee76-128">Se il cliente ha un Microsoft Technical Account Manager, il nome e le informazioni di contatto del TAM</span><span class="sxs-lookup"><span data-stu-id="9ee76-128">If the customer has a Microsoft Technical Account Manager, the TAM's name and contact information</span></span>
