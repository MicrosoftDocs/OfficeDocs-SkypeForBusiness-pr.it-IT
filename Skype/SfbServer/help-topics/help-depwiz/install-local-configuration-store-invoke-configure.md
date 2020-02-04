---
title: Installare una archivio di configurazione locale (Configure)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeployReplicaConfig
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 92dccbca-7a5b-4064-9f2e-964b8e62433c
description: Per avviare l'installazione del database che conterrà la copia locale di sola lettura di Central Management store, è possibile selezionare tra il recupero della configurazione definita pubblicata tramite Generatore di topologia dalla centrale già installata e configurata Management Store oppure leggendo la configurazione definita da altri elementi multimediali. Per un computer che si trova nella rete interna dell'organizzazione, selezionare Recupera automaticamente la configurazione dall'Central Management store.
ms.openlocfilehash: dcbcbea9b941c83c28ebce5ba9b65cad1c38be9d
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41687629"
---
# <a name="install-local-configuration-store-invoke-configure"></a><span data-ttu-id="6b869-104">Installare una archivio di configurazione locale (Configure)</span><span class="sxs-lookup"><span data-stu-id="6b869-104">Install Local Configuration Store Invoke (Configure)</span></span>
 
<span data-ttu-id="6b869-105">Per avviare l'installazione del database che conterrà la copia locale di sola lettura di Central Management store, è possibile selezionare tra il recupero della configurazione definita pubblicata tramite Generatore di topologia dalla centrale già installata e configurata Management Store oppure leggendo la configurazione definita da altri elementi multimediali.</span><span class="sxs-lookup"><span data-stu-id="6b869-105">To begin the installation of the database that will hold the local read-only copy of the Central Management store, you select between retrieving the defined configuration published by using Topology Builder from the already installed and configured Central Management store, or reading the defined configuration from other media.</span></span> <span data-ttu-id="6b869-106">Per un computer che si trova nella rete interna dell'organizzazione, selezionare **Recupera automaticamente la configurazione dall'Central Management store**.</span><span class="sxs-lookup"><span data-stu-id="6b869-106">For a machine that is on your organization's internal network, select **Retrieve configuration automatically from the Central Management Store**.</span></span>
  
<span data-ttu-id="6b869-107">Se si sta installando una replica di Central Management store in un server perimetrale, è possibile selezionare la copia esportata del documento di configurazione da un supporto portatile, ad esempio un'unità flash USB, un'unità disco rigido USB, un CD-ROM o un altro elemento multimediale.</span><span class="sxs-lookup"><span data-stu-id="6b869-107">If you are installing a replica of the Central Management store on an Edge Server, you select to read the exported copy of the configuration document from portable media, such as a USB flash drive, USB hard disk drive, CD-ROM, or other media.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="6b869-108">Se si sta installando l'archivio di configurazione locale in un server perimetrale, le informazioni di configurazione devono essere in un formato esportato dall'archivio di gestione centrale eseguendo il cmdlet di Windows PowerShell:`Export-CsConfiguration -FileName <ConfigurationFilePath.zip>`</span><span class="sxs-lookup"><span data-stu-id="6b869-108">If you are installing the Local Configuration store on an Edge Server, the configuration information must be in a format that was exported from the Central Management store by running the Windows PowerShell cmdlet:  `Export-CsConfiguration -FileName <ConfigurationFilePath.zip>`</span></span>
  
<span data-ttu-id="6b869-109">Dopo aver selezionato l'opzione appropriata, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="6b869-109">After you have selected the appropriate option, click **Next**.</span></span>
  

