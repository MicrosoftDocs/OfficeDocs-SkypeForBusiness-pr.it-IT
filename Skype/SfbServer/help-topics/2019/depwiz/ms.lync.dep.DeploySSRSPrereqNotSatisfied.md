---
title: SQL Server Reporting Services (prerequisiti non soddisfatti)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeploySSRSPrereqNotSatisfied
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6be29df-b882-4ba8-ba40-8062eb3bb14d
ROBOTS: NOINDEX, NOFOLLOW
description: Questa pagina verrà visualizzata se nell'infrastruttura non è distribuito alcun Monitoring Server. Questo significa che i requisiti minimi per la distribuzione dei rapporti sui Monitoring Server non sono stati soddisfatti.
ms.openlocfilehash: 6136979e900fa9b1bef0c20f600ad1a1699b2a06
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190985"
---
# <a name="sql-server-reporting-services-prerequisites-not-satisfied"></a>SQL Server Reporting Services (prerequisiti non soddisfatti)

Questa pagina verrà visualizzata se nell'infrastruttura non è distribuito alcun Monitoring Server. Questo significa che i requisiti minimi per la distribuzione dei rapporti sui Monitoring Server non sono stati soddisfatti.

Per risolvere il problema, verificare che sia stato aggiunto un server di monitoraggio al dominio, che sia definito in Generatore di topologia e che la topologia sia stata pubblicata. SQL Server Reporting Services deve essere disponibile anche in SQL Server e installato come funzionalità nel database del server di monitoraggio in SQL Server.

Per informazioni dettagliate, vedere [installare report di monitoraggio in Skype for Business Server](../../../deploy/deploy-monitoring/install-monitoring-reports.md) e [distribuzione del monitoraggio](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).


