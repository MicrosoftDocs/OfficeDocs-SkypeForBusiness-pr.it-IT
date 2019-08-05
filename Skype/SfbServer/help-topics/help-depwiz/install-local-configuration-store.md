---
title: Installare un archivio di configurazione locale
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/13/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainInstallReplica
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d9c4bcc2-11a7-4d4d-858d-224db217ad32
description: Per iniziare l'installazione di un nuovo server di ruoli di Skype for Business Server 2015, è necessario prima di tutto installare il server SQL locale che ospiterà l'archivio di configurazione locale. L'archivio di configurazione locale fungerà da replica di sola lettura di Skype for Business Server Central Management store (CMS). È necessario essere connessi al server in cui si sta eseguendo il passaggio Installa archivio di configurazione locale come amministratori locali e appartenere al gruppo RTCUniversalServerAdmins o RTCUniversalGlobalReadOnlyGroup. Se si sta eseguendo l'installazione in un Edge Server, non è necessario essere membri del gruppo RTCUniversalServerAdmins o RTCUniversalGlobalReadOnlyGroup. Il documento di definizione del generatore di topologia verrà letto dal documento di definizione esportato anziché dall'Central Management store. Per esportare il documento di definizione del generatore di topologia e renderlo disponibile per gli Edge Server, vedere l'argomento esportare la topologia e copiarla in elementi multimediali esterni per l'installazione di Edge.
ms.openlocfilehash: c3da29e6c9630b22e7ae947f9b23ab5dbeebd13c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36195242"
---
# <a name="install-local-configuration-store"></a>Installare un archivio di configurazione locale

Per iniziare l'installazione di un nuovo server di ruoli di Skype for Business Server 2015, è necessario prima di tutto installare il server SQL locale che ospiterà l'archivio di configurazione locale. L'archivio di configurazione locale fungerà da replica di sola lettura di Skype for Business Server Central Management store (CMS). È necessario essere connessi al server in cui si sta eseguendo il passaggio **Installa archivio di configurazione locale** come amministratori locali e appartenere al gruppo RTCUniversalServerAdmins o RTCUniversalGlobalReadOnlyGroup. Se si sta eseguendo l'installazione in un Edge Server, non è necessario essere membri del gruppo RTCUniversalServerAdmins o RTCUniversalGlobalReadOnlyGroup. Il documento di definizione del generatore di topologia verrà letto dal documento di definizione esportato anziché dall'Central Management store. Per esportare il documento di definizione del generatore di topologia e renderlo disponibile per gli Edge Server, vedere l'argomento [esportare la topologia e copiarla in elementi multimediali esterni per l'installazione di Edge](https://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx).

Per avviare l'installazione, eseguire le operazioni seguenti:

1. Nella pagina Skype for Business Server 2015, accanto a **Step1: install Local Configuration Store**, fare clic su **Esegui**.

2. Nella pagina **Configurazione server locale** verificare che l'opzione **Recupera configurazione automaticamente da Archivio di gestione centrale** sia selezionata e quindi fare clic su **Avanti**.

3. Al termine dell'installazione con configurazione del server locale, fare clic su **Fine**.

> [!NOTE]
> L'installazione di SQL Server locale può richiedere del tempo. Durante l'installazione di SQL Server, gli aggiornamenti sullo stato di avanzamento non verranno visualizzati nella schermata Riepilogo installazioni. Se si vuole monitorare lo stato di avanzamento dell'installazione, usare Gestione attività per guardare la configurazione di SQL Server.


