---
title: Installare un archivio di configurazione locale (Configure)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployReplicaConfig
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 92dccbca-7a5b-4064-9f2e-964b8e62433c
description: Per avviare l'installazione del database che conterrà la copia locale di sola lettura dell'archivio di gestione centrale, è possibile scegliere tra il recupero della configurazione definita pubblicata tramite Generatore di topologie dall'archivio di gestione centrale già installato e configurato o la lettura della configurazione definita da altri supporti. Per un computer che si trova nella rete interna dell'organizzazione, selezionare Recupera automaticamente la configurazione dall'archivio di gestione centrale.
ms.openlocfilehash: f0e2f54e83831cf6ad626b5d83cf068f40110f07
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827206"
---
# <a name="install-local-configuration-store-invoke-configure"></a>Installare un archivio di configurazione locale (configurazione)
 
Per avviare l'installazione del database che conterrà la copia locale di sola lettura dell'archivio di gestione centrale, è possibile scegliere tra il recupero della configurazione definita pubblicata tramite Generatore di topologie dall'archivio di gestione centrale già installato e configurato o la lettura della configurazione definita da altri supporti. Per un computer che si trova nella rete interna dell'organizzazione, selezionare **Recupera automaticamente la configurazione dall'archivio di gestione centrale**.
  
Se si sta installando una replica dell'archivio di gestione centrale in un server perimetrale, scegliere di leggere la copia esportata del documento di configurazione da un supporto di memorizzazione portatile, ad esempio un'unità flash USB, un disco rigido USB, un CD-ROM o un altro supporto. 
  
> [!IMPORTANT]
> Se si sta installando l'archivio di configurazione locale in un server perimetrale, le informazioni di configurazione devono essere in un formato esportato dall'archivio di gestione centrale eseguendo il cmdlet di Windows PowerShell:  `Export-CsConfiguration -FileName <ConfigurationFilePath.zip>`
  
Dopo avere selezionato l'opzione appropriata, fare clic su **Avanti**.
  

