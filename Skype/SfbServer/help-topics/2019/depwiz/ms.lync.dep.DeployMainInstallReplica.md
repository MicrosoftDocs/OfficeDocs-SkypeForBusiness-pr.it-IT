---
title: Installare l'archivio di configurazione locale
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainInstallReplica
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: d9c4bcc2-11a7-4d4d-858d-224db217ad32
ROBOTS: NOINDEX, NOFOLLOW
description: Per iniziare l'installazione di un nuovo server Skype for Business Server ruolo, è necessario innanzitutto installare l'SQL Server locale che ospiterà l'archivio di configurazione locale. L'archivio di configurazione locale fungerà da replica di sola lettura dell Skype for Business Server di gestione centrale .
ms.openlocfilehash: 993eaa4e07a1b14e1ddeef11c80a15b4869b7719
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60738662"
---
# <a name="install-local-configuration-store"></a>Installare l'archivio di configurazione locale

Per iniziare l'installazione di un nuovo server Skype for Business Server ruolo, è necessario innanzitutto installare l'SQL Server locale che ospiterà l'archivio di configurazione locale. L'archivio di configurazione locale fungerà da replica di sola lettura dell Skype for Business Server di gestione centrale . È necessario essere connessi al server in cui si sta eseguendo il passaggio **Installa archivio di configurazione locale** come amministratori locali e appartenere al gruppo RTCUniversalServerAdmins o RTCUniversalGlobalReadOnlyGroup. Se si sta eseguendo l'installazione in un Edge Server, non è necessario essere membri del gruppo RTCUniversalServerAdmins o RTCUniversalGlobalReadOnlyGroup. Il documento di definizione di Generatore di topologie verrà letto dal documento di definizione esportato anziché dall'archivio di gestione centrale. Per esportare il documento di definizione di Generatore di topologie e renderlo disponibile per i server perimetrali, vedere l'argomento[Export Your Topology and Copy It to External Media for Edge Installation](/previous-versions/office/lync-server-2013/lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation).

Per avviare l'installazione, eseguire le operazioni seguenti:

1. Nella pagina Skype for Business Server, accanto a **Passaggio 1: Installare l'archivio di configurazione locale,** fare clic su **Esegui.**

2. Nella pagina **Configurazione server** locale verificare  che l'opzione Recupera configurazione automaticamente dall'archivio di gestione centrale sia selezionata e quindi fare clic su **Avanti.**

3. Al termine dell'installazione con configurazione del server locale, fare clic su **Fine**.

> [!NOTE]
> L'installazione dell'SQL Server locale può richiedere del tempo. Gli aggiornamenti non verranno visualizzati nella schermata di riepilogo dell'installazione durante SQL Server'installazione. Se si desidera monitorare l'avanzamento dell'installazione, utilizzare Task Manager per controllare l'SQL Server configurazione.