---
title: Aggiungere Office Web Apps Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddOfficeWebAppsServerPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8825dfb1-4b3d-4e01-ba4a-2bd800c6de3b
ROBOTS: NOINDEX, NOFOLLOW
description: 'La procedura guidata Definisci nuovo server Office Web Apps definisce un nuovo server Office Web Apps nella distribuzione. È necessario inserire le informazioni seguenti:'
ms.openlocfilehash: 84ebc3b3ca7a413d81b4a36e62cc33a4f3fd91f0
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095780"
---
# <a name="add-office-web-apps-server"></a>Aggiungere Office Web Apps Server

La **procedura guidata Definisci nuovo server Office Web Apps** definisce un nuovo server Office Web Apps nella distribuzione. È necessario inserire le informazioni seguenti:

 **FQDN server Office Web Apps**: digitare il nome di dominio completo del server che ospiterà il server Office Web Apps

 **URL individuazione server Office Web Apps**: Digitare l'URL (Uniform Resource Locator) completo del server Office Web Apps

> [!TIP]
> Il comportamento predefinito dell'URL di individuazione del **server Office Web Apps** è creare l'URL in base al nome di dominio completo del server Office Web Apps nel formato: `https://<FQDN of the Office Web Apps Server/hosting/discovery` . Nella maggior parte dei casi non è necessario modificare il formato predefinito. Potrebbe essere necessario modificare il formato predefinito nel caso in cui il server Office Web Apps e l'URL di individuazione del server Office Web Apps siano diversi. Ad esempio, il server Office Web Apps viene posizionato nella rete perimetrale e avrà un URL diverso in base alla posizione.

 Server Office Web Apps distribuito in una rete **esterna,ovvero perimetro/Internet:** selezionare la casella di controllo se il server Office Web Apps è posizionato all'esterno del firewall interno, ad esempio la rete perimetrale, la rete esterna o un'altra area di rete diversa dalla rete interna.

## <a name="see-also"></a>Vedere anche

[Componenti e topologie per le conferenze](/previous-versions/office/lync-server-2013/lync-server-2013-components-and-topologies-for-conferencing)