---
title: Aggiungere Office Web Apps Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: 9e1726ea4b536e46fdbca5ec3eddce25358cbbbb
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218727"
---
# <a name="add-office-web-apps-server"></a>Aggiungere Office Web Apps Server

La procedura guidata **Definisci nuovo server Office Web Apps** definisce un nuovo server Office Web Apps nella distribuzione. È necessario inserire le informazioni seguenti:

 **FQDN del server Office Web Apps**: digitare il nome di dominio completo del server che ospiterà il server Office Web Apps

 **URL di individuazione del server Office Web Apps**: digitare l'URL (Uniform Resource Locator) completo del server Office Web Apps

> [!TIP]
> Il comportamento predefinito dell' **URL di individuazione del server Office Web Apps** consiste nel creare l'URL in base al nome di dominio completo del server Office Web Apps nel formato seguente: `https://<FQDN of the Office Web Apps Server/hosting/discovery` . Nella maggior parte dei casi, non è necessario modificare il formato predefinito. Potrebbe essere necessario modificare il formato predefinito nel caso in cui il server Office Web Apps e l'URL di individuazione del server Office Web Apps debbano essere diversi. Ad esempio, il server Office Web Apps è posizionato nella rete perimetrale e avrà un URL diverso in base al percorso.

 Il **Server Office Web Apps è distribuito in una rete esterna (perimetro/Internet)**: selezionare questa casella di controllo se il server Office Web Apps è posizionato all'esterno del firewall interno, ad esempio la rete perimetrale, la rete esterna o un'altra area di rete diversa da quella della rete interna.

## <a name="see-also"></a>Vedere anche

[Componenti e topologie per le conferenze](https://technet.microsoft.com/library/eb83052a-3360-4ba1-a6a0-6ee419942809.aspx)
