---
title: Espansione delle impostazioni del trunk
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.TrunkSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d00e8f4-e599-4094-a4a1-34fd6e8a5580
ROBOTS: NOINDEX, NOFOLLOW
description: 'Per modificare le impostazioni di un trunk SIP, eseguire le operazioni seguenti:'
ms.openlocfilehash: 55df4a410f4d052d6dc886f609ddfc979e1a9bb8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36191282"
---
# <a name="trunk-settings-expander"></a>Espansione delle impostazioni del trunk

Per modificare le impostazioni di un trunk SIP, eseguire le operazioni seguenti:

 **Nome trunk** è un campo obbligatorio che identifica in modo univoco il trunk SIP nella distribuzione.

 **Gateway PSTN associato**: selezionare un gateway PSTN precedentemente definito nella distribuzione.

 **Porta di attesa per gateway IP/PSTN**: indica la porta TCP/IP sulla quale il gateway attenderà le richieste. Il valore è obbligatorio e può variare a seconda del fornitore del gateway, ma l'impostazione predefinita corrisponde alla porta 5067.

 **Protocollo trasporto SIP**: il protocollo usato è TCP o TLS. TLS corrisponde all'impostazione predefinita. Per determinare il protocollo supportato dal gateway in uso, vedere la documentazione del fornitore del gateway. L'impostazione predefinita TLS deve essere considerata la scelta più sicura, se il gateway supporta tale protocollo.

 **Mediation Server associato**: selezionare un Mediation Server esistente dalla distribuzione da associare al trunk SIP.

> [!NOTE]
> Solo il trunk radice può essere associato a un Mediation Server.

 **Porta Mediation Server associata**: valore obbligatorio, impostato sul valore configurato per l'ascolto del server Mediation.

![Espansione delle impostazioni del trunk](../../../media/Trunk_Settings_Expander.jpg)

## <a name="see-also"></a>Vedere anche

[Elenco di controllo della distribuzione SIP trunking](https://technet.microsoft.com/library/94f4f03e-19d5-4198-92be-e4076dbb959a.aspx)

[Componenti e topologie per il trunking SIP](https://technet.microsoft.com/library/8ed9a9d0-517e-4f36-a131-22cdafa257fa.aspx)
