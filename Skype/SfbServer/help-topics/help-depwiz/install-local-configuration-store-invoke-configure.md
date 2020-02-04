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
# <a name="install-local-configuration-store-invoke-configure"></a>Installare una archivio di configurazione locale (Configure)
 
Per avviare l'installazione del database che conterrà la copia locale di sola lettura di Central Management store, è possibile selezionare tra il recupero della configurazione definita pubblicata tramite Generatore di topologia dalla centrale già installata e configurata Management Store oppure leggendo la configurazione definita da altri elementi multimediali. Per un computer che si trova nella rete interna dell'organizzazione, selezionare **Recupera automaticamente la configurazione dall'Central Management store**.
  
Se si sta installando una replica di Central Management store in un server perimetrale, è possibile selezionare la copia esportata del documento di configurazione da un supporto portatile, ad esempio un'unità flash USB, un'unità disco rigido USB, un CD-ROM o un altro elemento multimediale. 
  
> [!IMPORTANT]
> Se si sta installando l'archivio di configurazione locale in un server perimetrale, le informazioni di configurazione devono essere in un formato esportato dall'archivio di gestione centrale eseguendo il cmdlet di Windows PowerShell:`Export-CsConfiguration -FileName <ConfigurationFilePath.zip>`
  
Dopo aver selezionato l'opzione appropriata, fare clic su **Avanti**.
  

