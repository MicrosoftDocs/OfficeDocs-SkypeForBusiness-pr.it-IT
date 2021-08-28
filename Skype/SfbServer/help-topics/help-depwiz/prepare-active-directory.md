---
title: Preparazione di Active Directory
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainADPrep
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: a8c96311-9e1c-4d39-9870-681fd4e272ff
description: Per iniziare l'installazione di Skype for Business Server 2015, è necessario preparare lo schema, la foresta e i domini di Servizi di dominio Active Directory che ospiteranno server e utenti. La Skype for Business Server guidata guiderà l'utente attraverso i passaggi necessari per preparare Active Directory, iniziando con lo schema e quindi nella preparazione della foresta. Dopo aver confermato che la replica di Active Directory ha avuto esito positivo, preparare ogni dominio che ospiterà utenti o server.
ms.openlocfilehash: 1a50936858c2a6d40b92fca3c5fc6e6663a00bb3
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58602831"
---
# <a name="prepare-active-directory"></a>Preparazione di Active Directory

Per iniziare l'installazione di Skype for Business Server 2015, è necessario preparare lo schema, la foresta e i domini di Servizi di dominio Active Directory che ospiteranno server e utenti. La Skype for Business Server guidata guiderà l'utente attraverso i passaggi necessari per preparare Active Directory, iniziando con lo schema e quindi nella preparazione della foresta. Dopo aver confermato che la replica di Active Directory ha avuto esito positivo, preparare ogni dominio che ospiterà utenti o server.

> [!IMPORTANT]
> Per preparare correttamente lo schema, è necessario essere connessi come membri del gruppo Enterprise Admins e del gruppo Schema Admins. Per preparare la foresta, è necessario essere connessi come membri del gruppo Enterprise Admins o come amministratori nella radice della foresta. Per preparare il dominio, è necessario essere connessi come membri del gruppo Domain Admins.

Per informazioni dettagliate sulle topologie di Active Directory supportate, vedere [Active Directory Support](/previous-versions/office/lync-server-2013/lync-server-2013-active-directory-support) nella documentazione relativa alla supportabilità. Per informazioni dettagliate sulla preparazione di Active Directory, vedere [Overview of Active Directory Domain Services Preparation](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-active-directory-domain-services-preparation) nella documentazione relativa alla distribuzione.