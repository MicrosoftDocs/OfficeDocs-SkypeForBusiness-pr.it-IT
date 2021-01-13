---
title: Associare i rapporti di monitoraggio a un database mirror in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 42b797c6-8db8-4ad7-886e-8ddf8deb06f9
description: 'Riepilogo: informazioni su come associare i rapporti di monitoraggio a un database mirror utilizzato da Skype for Business Server.'
ms.openlocfilehash: 4ce6d420f6b29a5c6160b9b220e5fd190a977f9d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802166"
---
# <a name="associate-monitoring-reports-with-a-mirror-database-in-skype-for-business-server"></a>Associare i rapporti di monitoraggio a un database mirror in Skype for Business Server 
 
**Riepilogo:** Informazioni su come associare i rapporti di monitoraggio a un database mirror utilizzato da Skype for Business Server.
  
## <a name="monitor-reports-with-a-mirror-database"></a>Monitorare i report con un database mirror

Se si configura un mirror per il database di monitoraggio, il database mirror avrà il sopravvento come database primario se si verifica un failover. Tuttavia, se si utilizzano i rapporti di monitoraggio di Skype for Business Server e si verifica un failover, potrebbe risultare che i rapporti di monitoraggio non si connettono al database mirror. Ciò è dovuto al fatto che, quando si installano i rapporti di monitoraggio, si specifica solo il percorso del database primario. non è possibile specificare il percorso del database mirror.
  
Per ottenere il failover automatico dei rapporti di monitoraggio per il database mirror, è necessario aggiungere il database mirror come "partner di failover" ai due database utilizzati dai report di monitoraggio (un database per i dati dei record dettagli chiamata e l'altro per i dati QoE). Tenere presente che questo passaggio deve essere eseguito dopo aver installato i report di monitoraggio. È possibile aggiungere le informazioni del partner di failover modificando manualmente i valori della stringa di connessione utilizzati dai due database. A tale scopo, completare la procedura seguente:
  
1. Utilizzare Internet Explorer per aprire la Home page di **SQL Server Reporting Services** . L'URL della Home page di Reporting Services include:
    
   - Il prefisso **http:** .
    
   - Il nome di dominio completo (FQDN) del computer in cui sono installati i servizi di Reporting (ad esempio, **ATL-SQL-001.litwareinc.com**).
    
   - La stringa di caratteri **/reports_**.
    
   - Nome dell'istanza del database in cui sono installati i rapporti di monitoraggio (ad esempio, **ARCHINST**).
    
     Ad esempio, se SQL Server Reporting Services è stato installato nel computer atl-sql-001.litwareinc.com e i rapporti di monitoraggio utilizzano l'istanza del database ARCHINST, l'URL della Home Page avrà l'aspetto seguente:
    
     **http://atl-sql-001.litwareinc.com/Reports_archinst**
    
2. Dopo aver eseguito l'accesso alla Home page di Reporting Services, fare clic su **ServerReports** e quindi su **Reports_Content**. Che porterà alla pagina **Reports_Content** per i rapporti di monitoraggio di Skype for Business Server.
    
3. Nella pagina **Reports_Content** fare clic sull'origine dati **CDRDB** .
    
4. Nella scheda **Proprietà** della pagina **CDRDB** cercare la casella di testo denominata **stringa di connessione**. La stringa di connessione corrente avrà un aspetto analogo al seguente:
    
    Data Source = (local) \archinst; Initial Catalog = LcsCDR
    
5. Modificare la stringa di connessione per includere il nome del server e l'istanza del database per il database mirror. Ad esempio, se il server è denominato ATL-mirror-001 e il database mirror si trova nell'istanza di ARCHINST, sarà necessario aggiungere per specificare il database mirror utilizzando la sintassi seguente:
    
    Partner di failover = ATL-mirror-001\Archinst
    
    La stringa di connessione modificata avrà l'aspetto seguente:
    
    Data Source = (local) \archinst; Partner di failover = ATL-mirror-001\Archinst; catalogo iniziale = LcsCDR
    
6. Dopo aver aggiornato la stringa di connessione, fare clic su **applica**.
    
7. Nella pagina **CDRDB** fare clic sul collegamento **Reports_Content** . Fare clic sull'origine dati di **QMSDB** e quindi modificare la stringa di connessione per il database QoE. Ad esempio:
    
    Data Source = (local) \archinst; Partner di failover = ATL-mirror-001\Archinst; catalogo iniziale = QoEMetrics
    
8. Fare clic su **Applica**.
    
## <a name="see-also"></a>Vedere anche

[Installare i rapporti di monitoraggio in Skype for Business Server](install-monitoring-reports.md)
  
[Utilizzo dei rapporti di monitoraggio in Skype for Business Server](../../manage/health-and-monitoring/monitoring-reports.md)
