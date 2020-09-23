---
title: Espansione delle impostazioni del trunk
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: 6393ef52859f32ad93d363faf36af3bd34530a9b
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/23/2020
ms.locfileid: "48215937"
---
# <a name="trunk-settings-expander"></a>Espansione delle impostazioni del trunk

Per modificare le impostazioni di un trunk SIP, eseguire le operazioni seguenti:

 **Nome trunk** è un campo obbligatorio che identifica in modo univoco il trunk SIP nella distribuzione.

 **Gateway PSTN associato**: selezionare un gateway PSTN precedentemente definito nella distribuzione.

 **Porta di attesa per gateway IP/PSTN**: indica la porta TCP/IP sulla quale il gateway attenderà le richieste. Il valore è obbligatorio e può variare a seconda del fornitore del gateway, ma l'impostazione predefinita corrisponde alla porta 5067.

 **Protocollo di trasporto SIP**: il protocollo usato è TCP o TLS. TLS corrisponde all'impostazione predefinita. Per determinare il protocollo supportato dal gateway in uso, vedere la documentazione del fornitore del gateway. L'impostazione predefinita TLS deve essere considerata la scelta più sicura, se il gateway supporta tale protocollo.

 **Mediation Server associato**: selezionare un Mediation Server esistente dalla distribuzione da associare al trunk SIP.

> [!NOTE]
> Solo il trunk radice può essere associato a un server di mediazione Lync Server 2010 o Lync Server 2013.

 **Porta Mediation Server associato**: valore obbligatorio, impostato sul valore configurato per l'ascolto del Mediation Server.

![Espansione delle impostazioni del trunk](../../media/Trunk_Settings_Expander.jpg)

## <a name="see-also"></a>Vedere anche

[Elenco di controllo per la distribuzione del trunking SIP](https://technet.microsoft.com/library/94f4f03e-19d5-4198-92be-e4076dbb959a.aspx)

[Componenti e topologie per il trunking SIP](https://technet.microsoft.com/library/8ed9a9d0-517e-4f36-a131-22cdafa257fa.aspx)
