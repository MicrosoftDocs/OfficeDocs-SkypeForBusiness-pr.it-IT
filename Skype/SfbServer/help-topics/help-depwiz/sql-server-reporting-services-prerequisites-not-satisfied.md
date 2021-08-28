---
title: SQL Server Reporting Services (prerequisiti non soddisfatti)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeploySSRSPrereqNotSatisfied
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: b6be29df-b882-4ba8-ba40-8062eb3bb14d
description: Questa pagina verrà visualizzata se nell'infrastruttura non è distribuito alcun Monitoring Server. Questo significa che i requisiti minimi per la distribuzione dei rapporti sui Monitoring Server non sono stati soddisfatti.
ms.openlocfilehash: 235dec8ce462a6aafe7a1c4746cdb01d5169d4b3
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58615972"
---
# <a name="sql-server-reporting-services-prerequisites-not-satisfied"></a>SQL Server Reporting Services (prerequisiti non soddisfatti)

Questa pagina verrà visualizzata se nell'infrastruttura non è distribuito alcun Monitoring Server. Questo significa che i requisiti minimi per la distribuzione dei rapporti sui Monitoring Server non sono stati soddisfatti.

Per risolvere questo problema, assicurarsi di avere un Monitoring Server aggiunto al dominio, che sia definito in Generatore di topologie e che la topologia sia stata pubblicata. SQL Server Reporting Services deve essere disponibile anche nel SQL Server e installato come funzionalità nel database di Monitoring Server nella SQL Server.

Per informazioni dettagliate, [vedere Install Monitoring Reports in Skype for Business Server 2015](../../deploy/deploy-monitoring/install-monitoring-reports.md) e [Deploying Monitoring.](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring)