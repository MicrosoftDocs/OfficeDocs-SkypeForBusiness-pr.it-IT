---
title: SQL Server Reporting Services (prerequisiti non soddisfatti)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeploySSRSPrereqNotSatisfied
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6be29df-b882-4ba8-ba40-8062eb3bb14d
description: Questa pagina verrà visualizzata se nell'infrastruttura non è distribuito alcun Monitoring Server. Questo significa che i requisiti minimi per la distribuzione dei rapporti sui Monitoring Server non sono stati soddisfatti.
ms.openlocfilehash: 94a20ce6f1a48e5eeed098777494e2d1f16597c1
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41687309"
---
# <a name="sql-server-reporting-services-prerequisites-not-satisfied"></a>SQL Server Reporting Services (prerequisiti non soddisfatti)

Questa pagina verrà visualizzata se nell'infrastruttura non è distribuito alcun Monitoring Server. Questo significa che i requisiti minimi per la distribuzione dei rapporti sui Monitoring Server non sono stati soddisfatti.

Per risolvere il problema, verificare che sia stato aggiunto un server di monitoraggio al dominio, che sia definito in Generatore di topologia e che la topologia sia stata pubblicata. SQL Server Reporting Services deve essere disponibile anche in SQL Server e installato come funzionalità nel database del server di monitoraggio in SQL Server.

Per informazioni dettagliate, vedere [installare i report di monitoraggio in Skype for Business Server 2015](../../deploy/deploy-monitoring/install-monitoring-reports.md) e [distribuire il monitoraggio](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).


