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
ms.openlocfilehash: 5de1fc9204e22b30431f692770e3ec663599dd73
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768479"
---
# <a name="skype-room-system-skype-for-business-software-license"></a><span data-ttu-id="a2c81-103">Skype room System: licenza per il software Skype for business</span><span class="sxs-lookup"><span data-stu-id="a2c81-103">Skype Room System: Skype for Business software license</span></span>
 
<span data-ttu-id="a2c81-104">Leggere questo argomento per informazioni su come verificare se si dispone di una licenza per il volume del software Skype for business.</span><span class="sxs-lookup"><span data-stu-id="a2c81-104">Read this topic to learn how to check whether you have a Skype for Business software volume license.</span></span> 
  
<span data-ttu-id="a2c81-105">Skype room System usa un client Skype for business installato, che richiede una licenza per il volume del software.</span><span class="sxs-lookup"><span data-stu-id="a2c81-105">Skype Room System uses an installed Skype for Business client, which requires a software volume license.</span></span> <span data-ttu-id="a2c81-106">Prima di distribuire il primo sistema per la sala Skype, Scopri lo stato di licenza del volume della distribuzione usando i server di gestione delle chiavi (KMS) o le chiavi di attivazione multiple (MAK).</span><span class="sxs-lookup"><span data-stu-id="a2c81-106">Before deploying the first Skype Room System, find out the volume license state of the deployment - using Key Management Servers (KMS) or Multiple Activation Keys (MAK).</span></span>
  
## <a name="key-management-servers-kms"></a><span data-ttu-id="a2c81-107">Server di gestione delle chiavi (KMS)</span><span class="sxs-lookup"><span data-stu-id="a2c81-107">Key Management Servers (KMS)</span></span>

<span data-ttu-id="a2c81-108">Se i KMS sono in posizione e distribuiscono le attivazioni di contratti multilicenza Skype for business, il sistema Skype room attiverà automaticamente il client Skype for business.</span><span class="sxs-lookup"><span data-stu-id="a2c81-108">If KMS are in place and will distribute Skype for Business Volume License activations, the Skype Room System will automatically activate the Skype for Business client.</span></span> <span data-ttu-id="a2c81-109">Per scoprire se i KMS sono in posizione:</span><span class="sxs-lookup"><span data-stu-id="a2c81-109">To find out if KMS are in place:</span></span>
  
<span data-ttu-id="a2c81-110">In un prompt dei comandi eseguire:`nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`</span><span class="sxs-lookup"><span data-stu-id="a2c81-110">From a command prompt, run:  `nslookup -type=srv _vlmcs._tcp >%temp%\kms.txt`</span></span>
  
<span data-ttu-id="a2c81-111">Per altre informazioni, vedere [come individuare gli host di Office e Windows KMS tramite DNS e rimuovere istanze non autorizzate](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx).</span><span class="sxs-lookup"><span data-stu-id="a2c81-111">For more information, see [How to discover Office and Windows KMS hosts via DNS and remove unauthorized instances](https://blogs.technet.com/b/odsupport/archive/2011/11/14/how-to-discover-kms-hosts-via-a-dns-query-and-remove-them-if-need-be.aspx).</span></span> 
  
<span data-ttu-id="a2c81-112">Per configurare un KMS, vedere [attivazione di KMS da office 2013](https://technet.microsoft.com/library/ee624357.aspx) e [GVLKs per l'attivazione di KMS e Active Directory di Office 2013](https://technet.microsoft.com/library/dn385360.aspx)</span><span class="sxs-lookup"><span data-stu-id="a2c81-112">To set up a KMS, see [KMS activation of Office 2013](https://technet.microsoft.com/library/ee624357.aspx) and [GVLKs for KMS and Active Directory activation of Office 2013](https://technet.microsoft.com/library/dn385360.aspx)</span></span>
  
<span data-ttu-id="a2c81-113">Chiave di licenza per il volume generico di Office 2013 per Lync: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (questa chiave fa sì che il sistema Skype room cerchi un KMS nella rete).</span><span class="sxs-lookup"><span data-stu-id="a2c81-113">Office 2013 Generic Volume License Key for Lync: 2MG3G-3BNTT-3MFW9-KDQW3-TCK7R (This key causes the Skype Room System to look for a KMS on the network.)</span></span>
  
## <a name="multiple-activation-keys-mak-from-the-volume-license-service-center-vlsc"></a><span data-ttu-id="a2c81-114">Più chiavi di attivazione (MAK) dal centro servizi Volume License (VLSC)</span><span class="sxs-lookup"><span data-stu-id="a2c81-114">Multiple Activation Keys (MAK) from the Volume License Service Center (VLSC)</span></span>

<span data-ttu-id="a2c81-115">Se il cliente usa qualsiasi altro software per contratti multilicenza, il reparto IT gestirà le attivazioni software e il contratto multilicenza (VLA) usando il VLSC.</span><span class="sxs-lookup"><span data-stu-id="a2c81-115">If the customer uses any other volume license software, the IT department will manage the software activations and Volume License Agreement (VLA) using the VLSC.</span></span> <span data-ttu-id="a2c81-116">Ciò consentirà inoltre alla società di acquistare le attivazioni di Skype for business VL, dopodiché la società può ottenere un MAK per l'input nella console di amministrazione di Skype room System.</span><span class="sxs-lookup"><span data-stu-id="a2c81-116">This will also enable the company to purchase Skype for Business VL activations, after which the company can obtain a MAK for input in the Skype Room System Admin Console.</span></span>
  
<span data-ttu-id="a2c81-117">Un cliente con un VLA deve conoscere le proprie credenziali di VLSC, che verranno usate per amministrare il contratto e ottenere MAK.</span><span class="sxs-lookup"><span data-stu-id="a2c81-117">A customer with a VLA must know their VLSC credentials, which will be used to administer the agreement and obtain MAK.</span></span> <span data-ttu-id="a2c81-118">Se non si è certi, il reparto Finanza del cliente dovrebbe essere in grado di verificare se il cliente ha pagato un VLA.</span><span class="sxs-lookup"><span data-stu-id="a2c81-118">If uncertain, the customer's finance department should be able to confirm if the customer has paid for a VLA.</span></span>
  
<span data-ttu-id="a2c81-119">Per ottenere un MAK, accedere al centro servizi contratti multilicenza per visualizzare i contratti e scaricare i codici Product Key (MAK).</span><span class="sxs-lookup"><span data-stu-id="a2c81-119">To obtain a MAK, access the Volume Licensing Service Center to view agreements and download product keys (MAK).</span></span> <span data-ttu-id="a2c81-120">Per altre informazioni, visitare il [centro servizi per contratti multilicenza](https://www.microsoft.com/Licensing/servicecenter/default.aspx).</span><span class="sxs-lookup"><span data-stu-id="a2c81-120">For more information, go to the [Volume Licensing Service Center](https://www.microsoft.com/Licensing/servicecenter/default.aspx).</span></span> 
  
## <a name="mak-for-office-365-without-vlsc-access"></a><span data-ttu-id="a2c81-121">MAK per Office 365 senza accesso VLSC</span><span class="sxs-lookup"><span data-stu-id="a2c81-121">MAK for Office 365 without VLSC access</span></span>

<span data-ttu-id="a2c81-122">Se il cliente non ha un contratto multilicenza, le attivazioni di Skype for business saranno molto più difficili da gestire.</span><span class="sxs-lookup"><span data-stu-id="a2c81-122">If the customer doesn't have a Volume License Agreement, Skype for Business activations will be much more difficult to manage.</span></span> <span data-ttu-id="a2c81-123">Tuttavia, i clienti di Office 365 senza VLSC Access possono ottenere un MAK promozionale fornendo le informazioni seguenti all'OEM che vende il sistema Skype room System:</span><span class="sxs-lookup"><span data-stu-id="a2c81-123">However, Office 365 customers without VLSC access can obtain a promotional MAK by providing the following information to the OEM selling the Skype Room System:</span></span>
  
- <span data-ttu-id="a2c81-124">Nome società</span><span class="sxs-lookup"><span data-stu-id="a2c81-124">Company name</span></span>
    
- <span data-ttu-id="a2c81-125">Nome del contatto di distribuzione, posta elettronica e numero di telefono</span><span class="sxs-lookup"><span data-stu-id="a2c81-125">Deployment contact name, email, and phone number</span></span>
    
- <span data-ttu-id="a2c81-126">Numero di sistemi distribuiti</span><span class="sxs-lookup"><span data-stu-id="a2c81-126">Number of systems deployed</span></span>
    
- <span data-ttu-id="a2c81-127">Data di distribuzione</span><span class="sxs-lookup"><span data-stu-id="a2c81-127">Deployment date</span></span>
    
- <span data-ttu-id="a2c81-128">Se il cliente ha un Technical Account Manager Microsoft, il nome e le informazioni di contatto del TAM</span><span class="sxs-lookup"><span data-stu-id="a2c81-128">If the customer has a Microsoft Technical Account Manager, the TAM's name and contact information</span></span>
    

