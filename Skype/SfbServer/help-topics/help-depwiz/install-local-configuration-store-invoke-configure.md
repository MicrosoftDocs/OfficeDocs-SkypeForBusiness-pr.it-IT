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
description: Per iniziare l'installazione del database che contenerà la copia locale di sola lettura dell'archivio di gestione centrale, è possibile scegliere se recuperare la configurazione definita pubblicata utilizzando Generatore di topologie dall'archivio di gestione centrale già installato e configurato oppure leggere la configurazione definita da altri supporti. Per un computer che si trova nella rete interna dell'organizzazione, selezionare Recupera configurazione automaticamente dall'archivio di gestione centrale.
ms.openlocfilehash: f0e2f54e83831cf6ad626b5d83cf068f40110f07
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827206"
---
# <a name="install-local-configuration-store-invoke-configure"></a><span data-ttu-id="0abbe-104">Installare un archivio di configurazione locale (configurazione)</span><span class="sxs-lookup"><span data-stu-id="0abbe-104">Install Local Configuration Store Invoke (Configure)</span></span>
 
<span data-ttu-id="0abbe-105">Per iniziare l'installazione del database che contenerà la copia locale di sola lettura dell'archivio di gestione centrale, è possibile scegliere se recuperare la configurazione definita pubblicata utilizzando Generatore di topologie dall'archivio di gestione centrale già installato e configurato oppure leggere la configurazione definita da altri supporti.</span><span class="sxs-lookup"><span data-stu-id="0abbe-105">To begin the installation of the database that will hold the local read-only copy of the Central Management store, you select between retrieving the defined configuration published by using Topology Builder from the already installed and configured Central Management store, or reading the defined configuration from other media.</span></span> <span data-ttu-id="0abbe-106">Per un computer che si trova nella rete interna dell'organizzazione, selezionare Recupera configurazione **automaticamente dall'archivio di gestione centrale.**</span><span class="sxs-lookup"><span data-stu-id="0abbe-106">For a machine that is on your organization's internal network, select **Retrieve configuration automatically from the Central Management Store**.</span></span>
  
<span data-ttu-id="0abbe-107">Se si sta installando una replica dell'archivio di gestione centrale in un server perimetrale, scegliere di leggere la copia esportata del documento di configurazione da un supporto di memorizzazione portatile, ad esempio un'unità flash USB, un disco rigido USB, un CD-ROM o un altro supporto.</span><span class="sxs-lookup"><span data-stu-id="0abbe-107">If you are installing a replica of the Central Management store on an Edge Server, you select to read the exported copy of the configuration document from portable media, such as a USB flash drive, USB hard disk drive, CD-ROM, or other media.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="0abbe-108">Se si installa l'archivio di configurazione locale in un server perimetrale, le informazioni di configurazione devono essere in un formato esportato dall'archivio di gestione centrale eseguendo il cmdlet Windows PowerShell:  `Export-CsConfiguration -FileName <ConfigurationFilePath.zip>`</span><span class="sxs-lookup"><span data-stu-id="0abbe-108">If you are installing the Local Configuration store on an Edge Server, the configuration information must be in a format that was exported from the Central Management store by running the Windows PowerShell cmdlet:  `Export-CsConfiguration -FileName <ConfigurationFilePath.zip>`</span></span>
  
<span data-ttu-id="0abbe-109">Dopo avere selezionato l'opzione appropriata, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="0abbe-109">After you have selected the appropriate option, click **Next**.</span></span>
  

