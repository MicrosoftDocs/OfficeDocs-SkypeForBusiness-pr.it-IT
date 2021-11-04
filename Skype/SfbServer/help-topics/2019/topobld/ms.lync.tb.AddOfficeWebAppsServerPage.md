---
title: Aggiungere Office Web Apps Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddOfficeWebAppsServerPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 8825dfb1-4b3d-4e01-ba4a-2bd800c6de3b
ROBOTS: NOINDEX, NOFOLLOW
description: 'La procedura guidata Define New Office Web Apps Server definisce un nuovo Office Web Apps Server nella distribuzione. È necessario inserire le informazioni seguenti:'
ms.openlocfilehash: d8f86890face6ae6a948a5006b101bc8585f16a4
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60766914"
---
# <a name="add-office-web-apps-server"></a>Aggiungere Office Web Apps Server

La **procedura guidata Define New Office Web Apps Server** definisce un nuovo Office Web Apps Server nella distribuzione. È necessario inserire le informazioni seguenti:

 **Office FQDN del server Web Apps:** digitare il nome di dominio completo del server che ospiterà il server Office Web Apps Server

 **Office'URL** di individuazione del server Web Apps: digitare l'URL (Uniform Resource Locator) completo del Office Web Apps Server

> [!TIP]
> Il comportamento predefinito dell'URL di individuazione Office **Web Apps Server** è quello di creare l'URL in base al nome di dominio completo del server Office Web Apps nel formato: `https://<FQDN of the Office Web Apps Server/hosting/discovery` . Nella maggior parte dei casi non è necessario modificare il formato predefinito. Potrebbe essere necessario modificare il formato predefinito nel caso in cui il server Office Web Apps e l'URL di individuazione Office Web Apps Server siano diversi. Ad esempio, il Office Web Apps Server viene posizionato nella rete perimetrale e avrà un URL diverso in base alla posizione.

 Office Web Apps Server viene distribuito in una rete esterna, ovvero **perimetrale/Internet:** selezionare la casella di controllo se il server app Web Office è posizionato all'esterno del firewall interno, ad esempio la rete perimetrale, la rete esterna o un'altra area di rete diversa dalla rete interna.

## <a name="see-also"></a>Vedere anche

[Componenti e topologie per le conferenze](/previous-versions/office/lync-server-2013/lync-server-2013-components-and-topologies-for-conferencing)