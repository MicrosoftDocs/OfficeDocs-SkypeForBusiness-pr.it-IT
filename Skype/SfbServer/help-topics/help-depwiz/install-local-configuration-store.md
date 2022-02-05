---
title: Installare l'archivio di configurazione locale
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 4/13/2015
audience: ITPro
ms.topic: article
f1.keywords:
  - CSH
ms.custom:
  - ms.lync.dep.DeployMainInstallReplica
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: d9c4bcc2-11a7-4d4d-858d-224db217ad32
description: 'Per iniziare l''installazione di un nuovo server Skype for Business Server 2015, è necessario innanzitutto installare il SQL Server locale che ospiterà l''archivio di configurazione locale. L''archivio di configurazione locale fungerà da replica di sola lettura dell''Skype for Business Server di gestione centrale ( CMS). È necessario essere connessi al server in cui si sta eseguendo il passaggio Installa archivio di configurazione locale come amministratori locali e appartenere al gruppo RTCUniversalServerAdmins o RTCUniversalGlobalReadOnlyGroup. Se si sta eseguendo l''installazione in un Edge Server, non è necessario essere membri del gruppo RTCUniversalServerAdmins o RTCUniversalGlobalReadOnlyGroup. Il documento di definizione di Generatore di topologie verrà letto dal documento di definizione esportato anziché dall''archivio di gestione centrale. Per esportare il documento di definizione di Generatore di topologie e renderlo disponibile per i server perimetrali, vedere l''argomento Export Your Topology and Copy It to External Media for Edge Installation.'
---

# <a name="install-local-configuration-store"></a>Installare l'archivio di configurazione locale

Per iniziare l'installazione di un nuovo server Skype for Business Server 2015, è necessario innanzitutto installare il SQL Server locale che ospiterà l'archivio di configurazione locale. L'archivio di configurazione locale fungerà da replica di sola lettura dell'Skype for Business Server di gestione centrale ( CMS). È necessario essere connessi al server in cui si sta eseguendo il passaggio **Installa archivio di configurazione locale** come amministratori locali e appartenere al gruppo RTCUniversalServerAdmins o RTCUniversalGlobalReadOnlyGroup. Se si sta eseguendo l'installazione in un Edge Server, non è necessario essere membri del gruppo RTCUniversalServerAdmins o RTCUniversalGlobalReadOnlyGroup. Il documento di definizione di Generatore di topologie verrà letto dal documento di definizione esportato anziché dall'archivio di gestione centrale. Per esportare il documento di definizione di Generatore di topologie e renderlo disponibile per i server perimetrali, vedere l'argomento [Export Your Topology and Copy It to External Media for Edge Installation](/previous-versions/office/lync-server-2013/lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation).

Per avviare l'installazione, eseguire le operazioni seguenti:

1. Nella pagina Skype for Business Server 2015, accanto a **Passaggio 1: Installare l'archivio di configurazione locale**, fare clic su **Esegui**.

2. Nella pagina **Configurazione server** locale verificare che l'opzione Recupera  la configurazione automaticamente dall'archivio di gestione centrale sia selezionata e quindi fare clic su **Avanti**.

3. Al termine dell'installazione con configurazione del server locale, fare clic su **Fine**.

> [!NOTE]
> L'installazione del SQL Server locale può richiedere del tempo. Gli aggiornamenti non verranno visualizzati nella schermata di riepilogo dell'installazione durante SQL Server'installazione. Se si desidera monitorare lo stato dell'installazione, utilizzare Task Manager per controllare l'SQL Server configurazione.