---
title: Installare un archivio di configurazione locale (Configure)
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployReplicaConfig
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: 92dccbca-7a5b-4064-9f2e-964b8e62433c
ROBOTS: NOINDEX, NOFOLLOW
description: Per iniziare l'installazione del database che contenerà la copia locale di sola lettura dell'archivio di gestione centrale, è necessario scegliere tra il recupero della configurazione definita pubblicata utilizzando Generatore di topologie dall'archivio di gestione centrale già installato e configurato oppure la lettura della configurazione definita da altri supporti. Per un computer che si trova nella rete interna dell'organizzazione, selezionare Recupera la configurazione automaticamente dall'archivio di gestione centrale.
ms.openlocfilehash: 78c5a1697c77ed1a370739dd173718a74ead148e
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60742802"
---
# <a name="install-local-configuration-store-invoke-configure"></a>Installare un archivio di configurazione locale (configurazione)
 
Per iniziare l'installazione del database che contenerà la copia locale di sola lettura dell'archivio di gestione centrale, è necessario scegliere tra il recupero della configurazione definita pubblicata utilizzando Generatore di topologie dall'archivio di gestione centrale già installato e configurato oppure la lettura della configurazione definita da altri supporti. Per un computer che si trova nella rete interna dell'organizzazione, selezionare Recupera la configurazione **automaticamente dall'archivio di gestione centrale.**
  
Se si sta installando una replica dell'archivio di gestione centrale in un server perimetrale, scegliere di leggere la copia esportata del documento di configurazione da un supporto di memorizzazione portatile, ad esempio un'unità flash USB, un disco rigido USB, un CD-ROM o un altro supporto. 
  
> [!IMPORTANT]
> Se si installa l'archivio di configurazione locale in un server perimetrale, le informazioni di configurazione devono essere in un formato esportato dall'archivio di gestione centrale eseguendo il cmdlet Windows PowerShell:`Export-CsConfiguration -FileName <ConfigurationFilePath.zip>`
  
Dopo avere selezionato l'opzione appropriata, fare clic su **Avanti**.
  

