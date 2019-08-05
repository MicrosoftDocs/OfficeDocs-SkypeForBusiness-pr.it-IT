---
title: Aggiungere Office Web Apps Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddOfficeWebAppsServerPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8825dfb1-4b3d-4e01-ba4a-2bd800c6de3b
ROBOTS: NOINDEX, NOFOLLOW
description: 'La procedura guidata Definisci nuovo server di Office Web Apps definisce un nuovo server di Office Web Apps nella distribuzione. Si compilano le informazioni seguenti:'
ms.openlocfilehash: f5cf9c686ec7d42db6db15021e28493507f954b5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36195747"
---
# <a name="add-office-web-apps-server"></a>Aggiungere Office Web Apps Server

La procedura guidata **Definisci nuovo server di Office Web Apps** definisce un nuovo server di Office Web Apps nella distribuzione. Si compilano le informazioni seguenti:

 **FQDN del server Office Web Apps**: digitare il nome di dominio completo del server che ospiterà il server Office Web Apps

 **URL di individuazione del server di Office Web Apps**: digitare l'URL (Uniform Resource Locator) completo del server Office Web Apps

> [!TIP]
> Il comportamento predefinito dell' **URL di individuazione del server di Office Web Apps** consiste nel creare l'URL in base al nome di dominio completo del server Office Web Apps `https://<FQDN of the Office Web Apps Server/hosting/discovery` nel formato:. Nella maggior parte dei casi non sarà necessario modificare il formato predefinito. Potrebbe essere necessario modificare il formato predefinito, se il server Office Web Apps e l'URL di individuazione del server di Office Web Apps devono essere diversi. Ad esempio, il server Office Web Apps viene posizionato nella rete perimetrale e avrà un URL diverso in base alla posizione.

 **Office Web Apps Server è distribuito in una rete esterna (ovvero perimetro/Internet)**: selezionare la casella di controllo se il server Office Web Apps è posizionato all'esterno del firewall interno, ad esempio la rete perimetrale, la rete esterna o un'altra area di rete Questa operazione non è uguale alla rete interna.

## <a name="see-also"></a>Vedere anche

[Componenti e topologie per i servizi di conferenza](https://technet.microsoft.com/library/eb83052a-3360-4ba1-a6a0-6ee419942809.aspx)
