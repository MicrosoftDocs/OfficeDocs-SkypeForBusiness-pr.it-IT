---
title: Associare i report di monitoraggio a un database mirror in Skype for Business Server
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
description: 'Riepilogo: informazioni su come associare i report di monitoraggio a un database mirror utilizzato Skype for Business Server.'
ms.openlocfilehash: 99b30eaf7388bfec71f55e2e3f1f784271a3258d1280953426291b1dbfe14750
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54304358"
---
# <a name="associate-monitoring-reports-with-a-mirror-database-in-skype-for-business-server"></a>Associare i report di monitoraggio a un database mirror in Skype for Business Server 
 
**Riepilogo:** Informazioni su come associare i report di monitoraggio a un database mirror utilizzato da Skype for Business Server.
  
## <a name="monitor-reports-with-a-mirror-database"></a>Monitorare i report con un database mirror

Se si configura un mirror per il database di monitoraggio, tale database mirror verrà preso in carico come database primario se si verifica un failover. Tuttavia, se si utilizzano Skype for Business Server di monitoraggio e si verifica un failover, è possibile che i rapporti di monitoraggio non si connettono al database mirror. Questo perché, quando si installa Report di monitoraggio, si specifica solo il percorso del database primario. non si specifica il percorso del database mirror.
  
Per fare in modo che i rapporti di monitoraggio esercitino automaticamente il failover nel database mirror, è necessario aggiungere il database mirror come "partner di failover" ai due database utilizzati dai rapporti di monitoraggio (un database per i dati del record dettagli chiamata e l'altro per i dati QoE). Tenere presente che questo passaggio deve essere eseguito dopo aver installato i rapporti di monitoraggio. È possibile aggiungere le informazioni sul partner di failover modificando manualmente i valori della stringa di connessione utilizzati da questi due database. A tale scopo, completare la procedura seguente:
  
1. Usa Internet Explorer per aprire la home page **SQL Server Reporting Services** pagina iniziale. L'URL della home page di Reporting Services include:
    
   - Prefisso **http:** .
    
   - Il nome di dominio completo (FQDN) del computer in cui è installato Reporting Services ( ad esempio, **atl-sql-001.litwareinc.com**).
    
   - Stringa di caratteri **/Reports_**.
    
   - Nome dell'istanza del database in cui sono installati i report di monitoraggio( ad esempio, **archinst**).
    
     Ad esempio, se SQL Server Reporting Services è stato installato nel computer atl-sql-001.litwareinc.com e i rapporti di monitoraggio utilizzano l'istanza di database archinst, l'URL della home page sarà simile al seguente:
    
     **http://atl-sql-001.litwareinc.com/Reports_archinst**
    
2. Dopo aver eseguito l'accesso alla home page di Reporting Services, fare clic su **ServerReports** e quindi su **Reports_Content**. Verrà visualizzata la pagina **Reports_Content** per i report di Skype for Business Server monitoraggio.
    
3. Nella pagina **Reports_Content** fare clic sull'origine dati **CDRDB.**
    
4. Nella scheda Proprietà della pagina  **CDRDB** cercare la casella di testo Stringa di **connessione.** La stringa di connessione corrente sarà simile alla seguente:
    
    Data source=(local)\archinst;initial catalog=LcsCDR
    
5. Modificare la stringa di connessione in modo da includere il nome del server e l'istanza del database per il database mirror. Ad esempio, se il server è denominato atl-mirror-001 e il database mirror si trova nell'istanza di archiviazione, sarà necessario aggiungere per specificare il database mirror utilizzando la sintassi seguente:
    
    Failover Partner=atl-mirror-001\archinst
    
    La stringa di connessione modificata sarà simile alla seguente:
    
    Data source=(local)\archinst; Partner di failover=atl-mirror-001\archinst;initial catalog=LcsCDR
    
6. Dopo aver aggiornato la stringa di connessione, fare clic su **Applica.**
    
7. Nella pagina **CDRDB** fare clic sul **Reports_Content** collegamento. Fare clic **sull'origine dati QMSDB** e quindi modificare la stringa di connessione per il database QoE. Ad esempio:
    
    Data source=(local)\archinst; Failover Partner=atl-mirror-001\archinst;initial catalog=QoEMetrics
    
8. Fare clic su **Applica**.
    
## <a name="see-also"></a>Vedere anche

[Installare i report di monitoraggio in Skype for Business Server](install-monitoring-reports.md)
  
[Utilizzo dei report di monitoraggio in Skype for Business Server](../../manage/health-and-monitoring/monitoring-reports.md)
