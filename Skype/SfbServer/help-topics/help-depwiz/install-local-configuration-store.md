---
title: Installare l'archivio di configurazione locale
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/13/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainInstallReplica
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d9c4bcc2-11a7-4d4d-858d-224db217ad32
description: Per iniziare l'installazione di un nuovo server dei ruoli di Skype for Business Server 2015, è necessario innanzitutto installare il SQL Server locale che ospiterà l'archivio di configurazione locale. L'archivio di configurazione locale fungerà da replica di sola lettura dell'archivio di gestione centrale di Skype for Business Server. È necessario essere connessi al server in cui si sta eseguendo il passaggio Installa archivio di configurazione locale come amministratori locali e appartenere al gruppo RTCUniversalServerAdmins o RTCUniversalGlobalReadOnlyGroup. Se si sta eseguendo l'installazione in un Edge Server, non è necessario essere membri del gruppo RTCUniversalServerAdmins o RTCUniversalGlobalReadOnlyGroup. Il documento di definizione di Generatore di topologie verrà letto dal documento di definizione esportato anziché dall'archivio di gestione centrale. Per esportare il documento di definizione di Generatore di topologie e renderlo disponibile per i server perimetrali, vedere l'argomento Export Your Topology and Copy It to External Media for Edge Installation.
ms.openlocfilehash: 630a3682d3dd5ca12381d5f5b549bb22121b579e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827146"
---
# <a name="install-local-configuration-store"></a>Installare l'archivio di configurazione locale

Per iniziare l'installazione di un nuovo server dei ruoli di Skype for Business Server 2015, è necessario innanzitutto installare il SQL Server locale che ospiterà l'archivio di configurazione locale. L'archivio di configurazione locale fungerà da replica di sola lettura dell'archivio di gestione centrale di Skype for Business Server. È necessario essere connessi al server in cui si sta eseguendo il passaggio **Installa archivio di configurazione locale** come amministratori locali e appartenere al gruppo RTCUniversalServerAdmins o RTCUniversalGlobalReadOnlyGroup. Se si sta eseguendo l'installazione in un Edge Server, non è necessario essere membri del gruppo RTCUniversalServerAdmins o RTCUniversalGlobalReadOnlyGroup. Il documento di definizione di Generatore di topologie verrà letto dal documento di definizione esportato anziché dall'archivio di gestione centrale. Per esportare il documento di definizione di Generatore di topologie e renderlo disponibile per i server perimetrali, vedere l'argomento [Export Your Topology and Copy It to External Media for Edge Installation.](https://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx)

Per avviare l'installazione, eseguire le operazioni seguenti:

1. Nella pagina Skype for Business Server 2015, accanto a **Passaggio 1: Installare l'archivio** di configurazione locale, fare clic su **Esegui.**

2. Nella pagina **Configurazione server** locale verificare  che l'opzione Recupera configurazione automaticamente dall'archivio di gestione centrale sia selezionata e quindi fare clic su **Avanti.**

3. Al termine dell'installazione con configurazione del server locale, fare clic su **Fine**.

> [!NOTE]
> L'installazione del SQL Server locale può richiedere del tempo. Gli aggiornamenti sullo stato non verranno visualizzati nella schermata di riepilogo dell'SQL Server durante l'installazione. Se si desidera monitorare l'avanzamento dell'installazione, utilizzare Gestione attività per controllare l'SQL Server configurazione.


