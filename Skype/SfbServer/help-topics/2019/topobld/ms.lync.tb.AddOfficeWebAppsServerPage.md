---
title: Aggiungere Office Online Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddOfficeWebAppsServerPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8825dfb1-4b3d-4e01-ba4a-2bd800c6de3b
ROBOTS: NOINDEX, NOFOLLOW
description: 'La procedura guidata Definisci nuovo server di Office Web Apps definisce un nuovo server di Office Web Apps nella distribuzione. Si compilano le informazioni seguenti:'
ms.openlocfilehash: 207feb9187c880d43a5ce92eb6e93c6a5eedd44f
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41702771"
---
# <a name="add-office-web-apps-server"></a>Aggiungere Office Online Server

La procedura guidata **Definisci nuovo server di Office Web Apps** definisce un nuovo server di Office Web Apps nella distribuzione. Si compilano le informazioni seguenti:

 **FQDN del server Office Web Apps**: digitare il nome di dominio completo del server che ospiterà il server Office Web Apps

 **URL di individuazione del server di Office Web Apps**: digitare l'URL (Uniform Resource Locator) completo del server Office Web Apps

> [!TIP]
> Il comportamento predefinito dell' **URL di individuazione del server di Office Web Apps** consiste nel creare l'URL in base al nome di dominio completo del server Office Web Apps `https://<FQDN of the Office Web Apps Server/hosting/discovery` nel formato:. Nella maggior parte dei casi non sarà necessario modificare il formato predefinito. Potrebbe essere necessario modificare il formato predefinito, se il server Office Web Apps e l'URL di individuazione del server di Office Web Apps devono essere diversi. Ad esempio, il server Office Web Apps viene posizionato nella rete perimetrale e avrà un URL diverso in base alla posizione.

 **Office Web Apps Server è distribuito in una rete esterna (ovvero perimetro/Internet)**: selezionare la casella di controllo se il server Office Web Apps è posizionato all'esterno del firewall interno, ad esempio la rete perimetrale, la rete esterna o un'altra area di rete diversa da quella della rete interna.

## <a name="see-also"></a>Vedere anche

[Componenti e topologie per i servizi di conferenza](https://technet.microsoft.com/library/eb83052a-3360-4ba1-a6a0-6ee419942809.aspx)
