---
title: Aggiungere Office Web Apps Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddOfficeWebAppsServerPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8825dfb1-4b3d-4e01-ba4a-2bd800c6de3b
description: 'La procedura guidata Definisci nuovo server Office Web Apps definisce un nuovo server Office Web Apps nella distribuzione. È necessario inserire le informazioni seguenti:'
ms.openlocfilehash: a0d0543576b75e0572abf3fd043a73369d2af136
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828596"
---
# <a name="add-office-web-apps-server"></a><span data-ttu-id="bbb0b-104">Aggiungere Office Web Apps Server</span><span class="sxs-lookup"><span data-stu-id="bbb0b-104">Add Office Web Apps Server</span></span>

<span data-ttu-id="bbb0b-105">La **procedura guidata Definisci nuovo server Office Web Apps** definisce un nuovo server Office Web Apps nella distribuzione.</span><span class="sxs-lookup"><span data-stu-id="bbb0b-105">The **Define New Office Web Apps Server** wizard defines a new Office Web Apps Server in your deployment.</span></span> <span data-ttu-id="bbb0b-106">È necessario inserire le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="bbb0b-106">You fill in the following information:</span></span>

 <span data-ttu-id="bbb0b-107">**FQDN server Office Web Apps:** digitare il nome di dominio completo del server che ospiterà il server Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="bbb0b-107">**Office Web Apps Server FQDN**: Type the fully qualified domain name of the server that will host the Office Web Apps Server</span></span>

 <span data-ttu-id="bbb0b-108">URL di individuazione **del server Office Web Apps:** digitare l'URL (Uniform Resource Locator) completo del server Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="bbb0b-108">**Office Web Apps Server discovery URL**: Type the full uniform resource locator (URL) of the Office Web Apps Server</span></span>

> [!TIP]
> <span data-ttu-id="bbb0b-109">Il comportamento predefinito dell'URL di individuazione del **server Office Web Apps** è la creazione dell'URL in base al nome di dominio completo del server Office Web Apps nel formato seguente: `https://<FQDN of the Office Web Apps Server/hosting/discovery` .</span><span class="sxs-lookup"><span data-stu-id="bbb0b-109">The default behavior of the **Office Web Apps Server discovery URL** is to create the URL based on the FQDN of the Office Web Apps Server in the format: `https://<FQDN of the Office Web Apps Server/hosting/discovery` .</span></span> <span data-ttu-id="bbb0b-110">Nella maggior parte dei casi non è necessario modificare il formato predefinito.</span><span class="sxs-lookup"><span data-stu-id="bbb0b-110">In most cases you will not need to change the default format.</span></span> <span data-ttu-id="bbb0b-111">Potrebbe essere necessario modificare il formato predefinito nel caso in cui il server Office Web Apps e l'URL di individuazione del server Office Web Apps siano diversi.</span><span class="sxs-lookup"><span data-stu-id="bbb0b-111">You may need to change the default format in the event that the Office Web Apps Server and the Office Web Apps Server discovery URL must be different.</span></span> <span data-ttu-id="bbb0b-112">Ad esempio, il server Office Web Apps viene inserito nella rete perimetrale e avrà un URL diverso in base al percorso.</span><span class="sxs-lookup"><span data-stu-id="bbb0b-112">For example, your Office Web Apps Server is placed in the perimeter network and will have a different URL based on the location.</span></span>

 <span data-ttu-id="bbb0b-113">Il server Office Web Apps viene distribuito in una rete **esterna( perimetro/Internet):** selezionare la casella di controllo se il server Office Web Apps è posizionato all'esterno del firewall interno, ad esempio la rete perimetrale, la rete esterna o un'altra area di rete diversa dalla rete interna.</span><span class="sxs-lookup"><span data-stu-id="bbb0b-113">**Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)**: Select the check box if your Office Web Apps Server is placed outside of your internal firewall, such as the perimeter network, external network, or other network zone that is not the same as your internal network.</span></span>

## <a name="see-also"></a><span data-ttu-id="bbb0b-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bbb0b-114">See also</span></span>

[<span data-ttu-id="bbb0b-115">Componenti e topologie per le conferenze</span><span class="sxs-lookup"><span data-stu-id="bbb0b-115">Components and Topologies for Conferencing</span></span>](https://technet.microsoft.com/library/eb83052a-3360-4ba1-a6a0-6ee419942809.aspx)
