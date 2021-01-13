---
title: Installare l'archivio di configurazione locale
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainInstallReplica
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: d9c4bcc2-11a7-4d4d-858d-224db217ad32
ROBOTS: NOINDEX, NOFOLLOW
description: Per iniziare l'installazione di un nuovo server di ruoli di Skype for Business Server, è necessario innanzitutto installare SQL Server locale che ospiterà l'archivio di configurazione locale. L'archivio di configurazione locale fungerà da replica di sola lettura dell'archivio di gestione centrale (CMS) di Skype for Business Server.
ms.openlocfilehash: dcaf00e0bd14daecb6d2859bf40463265a3d6bc6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833806"
---
# <a name="install-local-configuration-store"></a>Installare l'archivio di configurazione locale

Per iniziare l'installazione di un nuovo server di ruoli di Skype for Business Server, è necessario innanzitutto installare SQL Server locale che ospiterà l'archivio di configurazione locale. L'archivio di configurazione locale fungerà da replica di sola lettura dell'archivio di gestione centrale (CMS) di Skype for Business Server. È necessario essere connessi al server in cui si sta eseguendo il passaggio **Installa archivio di configurazione locale** come amministratori locali e appartenere al gruppo RTCUniversalServerAdmins o RTCUniversalGlobalReadOnlyGroup. Se si sta eseguendo l'installazione in un Edge Server, non è necessario essere membri del gruppo RTCUniversalServerAdmins o RTCUniversalGlobalReadOnlyGroup. Il documento di definizione del generatore di topologie verrà letto dal documento di definizione esportato anziché dall'archivio di gestione centrale. Per esportare il documento di definizione del generatore di topologie e renderlo disponibile ai server perimetrali, vedere l'argomento[esportare la topologia e copiarla su supporto esterno per l'installazione perimetrale](https://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx).

Per avviare l'installazione, eseguire le operazioni seguenti:

1. Nella pagina Skype for Business Server fare clic su **Esegui** accanto a **passaggio 1: installazione dell'archivio di configurazione locale**.

2. Nella pagina **Configurazione server locale** verificare che l'opzione **Recupera configurazione automaticamente dall'archivio di gestione centrale** sia selezionata e quindi fare clic su **Avanti**.

3. Al termine dell'installazione con configurazione del server locale, fare clic su **Fine**.

> [!NOTE]
> L'installazione di SQL Server locale può richiedere del tempo. Durante l'installazione di SQL Server non verranno visualizzati gli aggiornamenti relativi allo stato di avanzamento nella schermata di riepilogo delle installazioni. Se si desidera monitorare lo stato dell'installazione, utilizzare Gestione attività per guardare il programma di installazione di SQL Server.


