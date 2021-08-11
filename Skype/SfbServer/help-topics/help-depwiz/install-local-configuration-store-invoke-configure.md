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
description: Per iniziare l'installazione del database che contenerà la copia locale di sola lettura dell'archivio di gestione centrale, è necessario scegliere se recuperare la configurazione definita pubblicata utilizzando Generatore di topologie dall'archivio di gestione centrale già installato e configurato oppure leggere la configurazione definita da altri supporti. Per un computer che si trova nella rete interna dell'organizzazione, selezionare Recupera la configurazione automaticamente dall'archivio di gestione centrale.
ms.openlocfilehash: 6035603e638a8d1459310c8b73002b5c9e922fc76e166cbd880ad9614f161563
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54285116"
---
# <a name="install-local-configuration-store-invoke-configure"></a>Installare un archivio di configurazione locale (configurazione)
 
Per iniziare l'installazione del database che contenerà la copia locale di sola lettura dell'archivio di gestione centrale, è necessario scegliere se recuperare la configurazione definita pubblicata utilizzando Generatore di topologie dall'archivio di gestione centrale già installato e configurato oppure leggere la configurazione definita da altri supporti. Per un computer che si trova nella rete interna dell'organizzazione, selezionare Recupera la configurazione **automaticamente dall'archivio di gestione centrale.**
  
Se si sta installando una replica dell'archivio di gestione centrale in un server perimetrale, scegliere di leggere la copia esportata del documento di configurazione da un supporto di memorizzazione portatile, ad esempio un'unità flash USB, un disco rigido USB, un CD-ROM o un altro supporto. 
  
> [!IMPORTANT]
> Se si installa l'archivio di configurazione locale in un server perimetrale, le informazioni di configurazione devono essere in un formato esportato dall'archivio di gestione centrale eseguendo il cmdlet Windows PowerShell:`Export-CsConfiguration -FileName <ConfigurationFilePath.zip>`
  
Dopo avere selezionato l'opzione appropriata, fare clic su **Avanti**.
  

