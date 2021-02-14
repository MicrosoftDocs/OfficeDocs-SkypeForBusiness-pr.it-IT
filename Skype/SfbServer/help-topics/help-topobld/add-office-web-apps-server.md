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
# <a name="add-office-web-apps-server"></a>Aggiungere Office Web Apps Server

La **procedura guidata Definisci nuovo server Office Web Apps** definisce un nuovo server Office Web Apps nella distribuzione. È necessario inserire le informazioni seguenti:

 **FQDN server Office Web Apps:** digitare il nome di dominio completo del server che ospiterà il server Office Web Apps

 URL di individuazione **del server Office Web Apps:** digitare l'URL (Uniform Resource Locator) completo del server Office Web Apps

> [!TIP]
> Il comportamento predefinito dell'URL di individuazione del **server Office Web Apps** è la creazione dell'URL in base al nome di dominio completo del server Office Web Apps nel formato seguente: `https://<FQDN of the Office Web Apps Server/hosting/discovery` . Nella maggior parte dei casi non è necessario modificare il formato predefinito. Potrebbe essere necessario modificare il formato predefinito nel caso in cui il server Office Web Apps e l'URL di individuazione del server Office Web Apps siano diversi. Ad esempio, il server Office Web Apps viene inserito nella rete perimetrale e avrà un URL diverso in base al percorso.

 Il server Office Web Apps viene distribuito in una rete **esterna( perimetro/Internet):** selezionare la casella di controllo se il server Office Web Apps è posizionato all'esterno del firewall interno, ad esempio la rete perimetrale, la rete esterna o un'altra area di rete diversa dalla rete interna.

## <a name="see-also"></a>Vedere anche

[Componenti e topologie per le conferenze](https://technet.microsoft.com/library/eb83052a-3360-4ba1-a6a0-6ee419942809.aspx)
