---
title: Licenza software Skype for business per Skype room System
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
f1.keywords:
- NOCSH
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78a664ba-fefc-4423-ac8f-b58e6fbc2e55
description: Leggere questo argomento per informazioni su come verificare se si dispone di una licenza per il volume del software Skype for business.
ms.openlocfilehash: a44e95d8cd488e2b12e03ee9848ef3d1b254180c
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220926"
---
# <a name="skype-room-system-skype-for-business-software-license"></a><span data-ttu-id="323e0-103">Skype room System: licenza del software Skype for business</span><span class="sxs-lookup"><span data-stu-id="323e0-103">Skype Room System: Skype for Business software license</span></span>
 
<span data-ttu-id="323e0-104">Leggere questo argomento per informazioni su come verificare se si dispone di una licenza per il volume del software Skype for business.</span><span class="sxs-lookup"><span data-stu-id="323e0-104">Read this topic to learn how to check whether you have a Skype for Business software volume license.</span></span> 
  
<span data-ttu-id="323e0-105">Skype room System utilizza un client Skype for business installato, che richiede una licenza per il volume del software.</span><span class="sxs-lookup"><span data-stu-id="323e0-105">Skype Room System uses an installed Skype for Business client, which requires a software volume license.</span></span> <span data-ttu-id="323e0-106">Prima di distribuire il primo sistema di Skype room, individuare lo stato di licenza del volume della distribuzione, utilizzando i server di gestione delle chiavi (KMS) o più chiavi di attivazione (MAK).</span><span class="sxs-lookup"><span data-stu-id="323e0-106">Before deploying the first Skype Room System, find out the volume license state of the deployment - using Key Management Servers (KMS) or Multiple Activation Keys (MAK).</span></span>
  
## <a name="key-management-servers-kms"></a><span data-ttu-id="323e0-107">Server di gestione delle chiavi (KMS)</span><span class="sxs-lookup"><span data-stu-id="323e0-107">Key Management Servers (KMS)</span></span>

<span data-ttu-id="323e0-108">Se i KMS sono sul posto e distribuiscono le attivazioni con contratti multilicenza di Skype for business, il sistema Skype room attiverà automaticamente il client Skype for business.</span><span class="sxs-lookup"><span data-stu-id="323e0-108">If KMS are in place and will distribute Skype for Business Volume License activations, the Skype Room System will automatically activate the Skype for Business client.</span></span> <span data-ttu-id="323e0-109">Per sapere se il servizio di gestione delle chiavi è sul posto:</span><span class="sxs-lookup"><span data-stu-id="323e0-109">To find out if KMS are in place:</span></span>
  
<span data-ttu-id="323e0-110">Da un prompt dei comandi eseguire:`nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`</span><span class="sxs-lookup"><span data-stu-id="323e0-110">From a command prompt, run:  `nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`</span></span>
  
<span data-ttu-id="323e0-111">Per ulteriori informazioni, vedere [come individuare gli host del servizio di gestione delle chiavi di Office e Windows tramite DNS e rimuovere le istanze non autorizzate](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx).</span><span class="sxs-lookup"><span data-stu-id="323e0-111">For more information, see [How to discover Office and Windows KMS hosts via DNS and remove unauthorized instances](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx).</span></span> 
  
<span data-ttu-id="323e0-112">Per impostare un servizio di gestione delle chiavi, vedere l' [attivazione del servizio di gestione delle chiavi di office 2013](https://technet.microsoft.com/library/ee624357.aspx) e [GVLK for KMS and Active Directory activation of Office 2013](https://technet.microsoft.com/library/dn385360.aspx)</span><span class="sxs-lookup"><span data-stu-id="323e0-112">To set up a KMS, see [KMS activation of Office 2013](https://technet.microsoft.com/library/ee624357.aspx) and [GVLKs for KMS and Active Directory activation of Office 2013](https://technet.microsoft.com/library/dn385360.aspx)</span></span>
  
<span data-ttu-id="323e0-113">Chiave per contratti multilicenza di Office 2013 generici per Lync: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (questa chiave causa la ricerca di un servizio di gestione delle chiavi in una rete in Skype room System).</span><span class="sxs-lookup"><span data-stu-id="323e0-113">Office 2013 Generic Volume License Key for Lync: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (This key causes the Skype Room System to look for a KMS on the network.)</span></span>
  
## <a name="multiple-activation-keys-mak-from-the-volume-license-service-center-vlsc"></a><span data-ttu-id="323e0-114">Tasti di attivazione multipli (MAK) dal centro servizi per contratti multilicenza (VLSC)</span><span class="sxs-lookup"><span data-stu-id="323e0-114">Multiple Activation Keys (MAK) from the Volume License Service Center (VLSC)</span></span>

<span data-ttu-id="323e0-115">Se il cliente utilizza qualsiasi altro software per contratti multilicenza, il reparto IT gestirà le attivazioni software e il contratto multilicenza (VLA) utilizzando VLSC.</span><span class="sxs-lookup"><span data-stu-id="323e0-115">If the customer uses any other volume license software, the IT department will manage the software activations and Volume License Agreement (VLA) using the VLSC.</span></span> <span data-ttu-id="323e0-116">Ciò consentirà anche all'azienda di acquistare le attivazioni di Skype for business VL, dopo di che la società può ottenere un MAK per l'input nella console di amministrazione di Skype room System.</span><span class="sxs-lookup"><span data-stu-id="323e0-116">This will also enable the company to purchase Skype for Business VL activations, after which the company can obtain a MAK for input in the Skype Room System Admin Console.</span></span>
  
<span data-ttu-id="323e0-117">Un cliente con un VLA deve conoscere le credenziali di VLSC, che verranno utilizzate per amministrare il contratto e ottenere MAK.</span><span class="sxs-lookup"><span data-stu-id="323e0-117">A customer with a VLA must know their VLSC credentials, which will be used to administer the agreement and obtain MAK.</span></span> <span data-ttu-id="323e0-118">Se non si è certi, il reparto Finanze del cliente dovrebbe essere in grado di confermare se il cliente ha pagato un VLA.</span><span class="sxs-lookup"><span data-stu-id="323e0-118">If uncertain, the customer's finance department should be able to confirm if the customer has paid for a VLA.</span></span>
  
<span data-ttu-id="323e0-119">Per ottenere un MAK, accedere a Volume Licensing Service Center per visualizzare i contratti e scaricare i codici Product Key (MAK).</span><span class="sxs-lookup"><span data-stu-id="323e0-119">To obtain a MAK, access the Volume Licensing Service Center to view agreements and download product keys (MAK).</span></span> <span data-ttu-id="323e0-120">Per ulteriori informazioni, visitare il [centro servizi per contratti multilicenza](https://www.microsoft.com/Licensing/servicecenter/default.aspx).</span><span class="sxs-lookup"><span data-stu-id="323e0-120">For more information, go to the [Volume Licensing Service Center](https://www.microsoft.com/Licensing/servicecenter/default.aspx).</span></span> 
  
## <a name="mak-for-microsoft-365-or-office-365-without-vlsc-access"></a><span data-ttu-id="323e0-121">MAK per Microsoft 365 o Office 365 senza accesso di VLSC</span><span class="sxs-lookup"><span data-stu-id="323e0-121">MAK for Microsoft 365 or Office 365 without VLSC access</span></span>

<span data-ttu-id="323e0-122">Se il cliente non ha un contratto multilicenza, le attivazioni di Skype for business saranno molto più difficili da gestire.</span><span class="sxs-lookup"><span data-stu-id="323e0-122">If the customer doesn't have a Volume License Agreement, Skype for Business activations will be much more difficult to manage.</span></span> <span data-ttu-id="323e0-123">Tuttavia, i clienti di Microsoft 365 e Office 365 senza l'accesso di VLSC possono ottenere un MAK promozionale fornendo le seguenti informazioni all'OEM che vende il sistema della sala Skype:</span><span class="sxs-lookup"><span data-stu-id="323e0-123">However, Microsoft 365 and Office 365 customers without VLSC access can obtain a promotional MAK by providing the following information to the OEM selling the Skype Room System:</span></span>
  
- <span data-ttu-id="323e0-124">Nome della società</span><span class="sxs-lookup"><span data-stu-id="323e0-124">Company name</span></span>
    
- <span data-ttu-id="323e0-125">Nome del contatto di distribuzione, posta elettronica e numero di telefono</span><span class="sxs-lookup"><span data-stu-id="323e0-125">Deployment contact name, email, and phone number</span></span>
    
- <span data-ttu-id="323e0-126">Numero di sistemi distribuiti</span><span class="sxs-lookup"><span data-stu-id="323e0-126">Number of systems deployed</span></span>
    
- <span data-ttu-id="323e0-127">Data di distribuzione</span><span class="sxs-lookup"><span data-stu-id="323e0-127">Deployment date</span></span>
    
- <span data-ttu-id="323e0-128">Se il cliente ha un responsabile dell'account tecnico Microsoft, il nome e le informazioni di contatto del TAM</span><span class="sxs-lookup"><span data-stu-id="323e0-128">If the customer has a Microsoft Technical Account Manager, the TAM's name and contact information</span></span>
    

