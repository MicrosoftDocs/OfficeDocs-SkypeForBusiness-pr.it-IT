---
title: Preparazione di Active Directory
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainADPrep
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: a8c96311-9e1c-4d39-9870-681fd4e272ff
ROBOTS: NOINDEX, NOFOLLOW
description: Per iniziare l'installazione Skype for Business Server, è necessario preparare lo schema, la foresta e i domini di Servizi di dominio Active Directory che ospiteranno server e utenti. La Skype for Business Server guidata guiderà l'utente nei passaggi necessari per preparare Active Directory, iniziando con lo schema e quindi nella preparazione della foresta. Dopo aver confermato che la replica di Active Directory è riuscita, preparare ogni dominio che ospiterà utenti o server.
ms.openlocfilehash: 86c548f59f7f6d3613971ff8765f01f3a4aa68b7965c402e126cdd9b7fa0a0b6
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54282224"
---
# <a name="prepare-active-directory"></a>Preparazione di Active Directory

Per iniziare l'installazione Skype for Business Server, è necessario preparare lo schema, la foresta e i domini di Servizi di dominio Active Directory che ospiteranno server e utenti. La Skype for Business Server guidata guiderà l'utente nei passaggi necessari per preparare Active Directory, iniziando con lo schema e quindi nella preparazione della foresta. Dopo aver confermato che la replica di Active Directory è riuscita, preparare ogni dominio che ospiterà utenti o server.

> [!IMPORTANT]
> Per preparare correttamente lo schema, è necessario essere connessi come membri del gruppo Enterprise Admins e del gruppo Schema Admins. Per preparare la foresta, è necessario essere connessi come membri del gruppo Enterprise Admins o come amministratori nella radice della foresta. Per preparare il dominio, è necessario essere connessi come membri del gruppo Domain Admins.

Per informazioni dettagliate sulle topologie di Active Directory supportate, vedere [Active Directory Support](/previous-versions/office/lync-server-2013/lync-server-2013-active-directory-support) nella documentazione relativa alla supportabilità. Per informazioni dettagliate sulla preparazione di Active Directory, vedere [Overview of Active Directory Domain Services Preparation](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-active-directory-domain-services-preparation) nella documentazione relativa alla distribuzione.