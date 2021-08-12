---
title: Espansione delle impostazioni del trunk
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.TrunkSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d00e8f4-e599-4094-a4a1-34fd6e8a5580
description: 'Per modificare le impostazioni di un trunk SIP, eseguire le operazioni seguenti:'
ms.openlocfilehash: c29f7e62b047e06bfce20324a7edc8dc33d635ac416fb78ae31efaba63538141
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54290613"
---
# <a name="trunk-settings-expander"></a>Espansione delle impostazioni del trunk

Per modificare le impostazioni di un trunk SIP, eseguire le operazioni seguenti:

 **Nome trunk** è un campo obbligatorio che identifica in modo univoco il trunk SIP nella distribuzione.

 **Gateway PSTN associato**: selezionare un gateway PSTN precedentemente definito nella distribuzione.

 **Porta di attesa per gateway IP/PSTN**: indica la porta TCP/IP sulla quale il gateway attenderà le richieste. Il valore è obbligatorio e può variare a seconda del fornitore del gateway, ma l'impostazione predefinita corrisponde alla porta 5067.

 **Protocollo di trasporto SIP**: il protocollo usato è TCP o TLS. TLS corrisponde all'impostazione predefinita. Per determinare il protocollo supportato dal gateway in uso, vedere la documentazione del fornitore del gateway. L'impostazione predefinita TLS deve essere considerata la scelta più sicura, se il gateway supporta tale protocollo.

 **Mediation Server associato:** selezionare un Mediation Server esistente dalla distribuzione da associare al trunk SIP.

> [!NOTE]
> Solo il trunk radice può essere associato a un Mediation Server di Lync Server 2010 o Lync Server 2013.

 **Porta Mediation Server associata:** valore obbligatorio, impostato sul valore su cui il Mediation Server è configurato per l'ascolto.

![Espansione delle impostazioni del trunk](../../media/Trunk_Settings_Expander.jpg)

## <a name="see-also"></a>Vedere anche

[Elenco di controllo per la distribuzione del trunking SIP](/previous-versions/office/lync-server-2013/lync-server-2013-sip-trunk-deployment-checklist)

[Componenti e topologie per il trunking SIP](/previous-versions/office/lync-server-2013/lync-server-2013-components-and-topologies-for-sip-trunking)