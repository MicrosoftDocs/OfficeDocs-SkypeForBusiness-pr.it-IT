---
title: Modificare le impostazioni di Office Web Apps Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 8/19/2016
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.OfficeWebAppsServerSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7a4b91ff-ca11-4dde-852d-ec51d143968a
description: 'È possibile modificare le proprietà del Office Web Apps Server configurato. È possibile modificare le proprietà seguenti:'
ms.openlocfilehash: 2810d18878c1f9796f3e95653cdae4324f0921496abe2b72584511db6352f9f3
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54329790"
---
# <a name="edit-office-web-apps-server-settings"></a>Modificare le impostazioni di Office Web Apps Server

È possibile modificare le proprietà del Office Web Apps Server configurato. È possibile modificare le proprietà seguenti:

 **Office** FQDN server Web Apps : questa proprietà definisce il nome di dominio completo del server web apps di Office e deve corrispondere a un record A o AAAA (se viene utilizzato IPv6) host DNS (Domain Name System).

 **Office URL** di individuazione del server Web Apps : URL (Uniform Resource Locator) per l'accesso client al server app Web Office, potrebbe essere necessario modificare questo indirizzo dal valore predefinito se il server viene posizionato in un'altra area di rete diversa dalla rete interna per la distribuzione.

Selezionare la casella di controllo **Il server Office Web Apps è distribuito in una rete esterna** se il server è distribuito nella rete perimetrale o in un'altra area della rete esterna al firewall interno che separa la rete perimetrale, le reti meno attendibili e Internet dalla distribuzione interna.

![Office Espansione Impostazioni web app](../../media/OfficeWebApps_Settings_Expander.jpg)

## <a name="see-also"></a>Vedere anche

[Componenti e topologie per le conferenze](/previous-versions/office/lync-server-2013/lync-server-2013-components-and-topologies-for-conferencing)