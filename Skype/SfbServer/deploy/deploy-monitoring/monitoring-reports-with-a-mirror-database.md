---
title: Associare i report di monitoraggio a un database mirror in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 42b797c6-8db8-4ad7-886e-8ddf8deb06f9
description: 'Riepilogo: informazioni su come associare i report di monitoraggio a un database mirror usato da Skype for Business Server.'
ms.openlocfilehash: 0727a278b87edd0b3666b04d169dcd3460c8215c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36186593"
---
# <a name="associate-monitoring-reports-with-a-mirror-database-in-skype-for-business-server"></a>Associare i report di monitoraggio a un database mirror in Skype for Business Server 
 
**Riepilogo:** Informazioni su come associare i report di monitoraggio a un database mirror usato da Skype for Business Server.
  
## <a name="monitor-reports-with-a-mirror-database"></a>Monitorare i report con un database mirror

Se si configura uno specchio per il database di monitoraggio, il database mirror subentra come database principale se si verifica un failover. Tuttavia, se si usano i report di monitoraggio di Skype for Business Server e si verifica un failover, è possibile che i report di monitoraggio non si connettono al database mirror. Questo perché, quando si installano i report di monitoraggio, si specifica solo la posizione del database primario; non si specifica la posizione del database mirror.
  
Per ottenere i report di monitoraggio per il failover automatico nel database mirror, è necessario aggiungere il database mirror come "partner di failover" ai due database usati dai report di monitoraggio (un database per i dati del record di dettagli chiamata e l'altro per la qualità di Dati dell'esperienza (QoE)). Notare che questo passaggio deve essere eseguito dopo aver installato i report di monitoraggio. È possibile aggiungere le informazioni del partner di failover modificando manualmente i valori della stringa di connessione usati da questi due database. Per eseguire questa operazione, eseguire la procedura seguente:
  
1. Usare Internet Explorer per aprire la Home page di **SQL Server Reporting Services** . L'URL della Home page di Reporting Services include:
    
   - Prefisso **http:**
    
   - Il nome di dominio completo (FQDN) del computer in cui sono installati i servizi di Reporting (ad esempio, **ATL-SQL-001.litwareinc.com**).
    
   - La stringa di caratteri **/reports_**.
    
   - Nome dell'istanza del database in cui sono installati i report di monitoraggio, ad esempio **ARCHINST**.
    
     Ad esempio, se SQL Server Reporting Services è stato installato nel computer atl-sql-001.litwareinc.com e i report di monitoraggio usano l'istanza del database ARCHINST, l'URL della Home page sarà simile al seguente:
    
     **http://atl-sql-001.litwareinc.com/Reports_archinst**
    
2. Dopo avere eseguito l'accesso alla Home page di Reporting Services, fare clic su **ServerReports**e quindi su **Reports_Content**. Questo ti porterà alla pagina **Reports_Content** per i report di monitoraggio di Skype for Business Server.
    
3. Nella pagina **Reports_Content** fare clic sull'origine dati **CDRDB** .
    
4. Nella scheda **Proprietà** della pagina **CDRDB** cercare nella casella di testo la **stringa di connessione**con etichetta. La stringa di connessione corrente avrà un aspetto simile al seguente:
    
    Origine dati = (locale) \archinst; catalogo iniziale = LcsCDR
    
5. Modificare la stringa di connessione per includere il nome del server e l'istanza del database per il database mirror. Ad esempio, se il server è denominato ATL-mirror-001 e il database mirror si trova nell'istanza di ARCHINST, sarà necessario aggiungerlo per specificare il database mirror usando la sintassi seguente:
    
    Partner failover = ATL-mirror-001\Archinst
    
    La stringa di connessione modificata avrà un aspetto simile al seguente:
    
    Origine dati = (local) \archinst; Partner di failover = ATL-mirror-001\Archinst; catalogo iniziale = LcsCDR
    
6. Dopo aver aggiornato la stringa di connessione, fare clic su **applica**.
    
7. Nella pagina **CDRDB** fare clic sul collegamento **Reports_Content** . Fare clic sull'origine dati **QMSDB** e quindi modificare la stringa di connessione per il database QoE. Ad esempio:
    
    Origine dati = (local) \archinst; Partner di failover = ATL-mirror-001\Archinst; catalogo iniziale = QoEMetrics
    
8. Fare clic su **applica**.
    
## <a name="see-also"></a>Vedere anche

[Installare report di monitoraggio in Skype for Business Server](install-monitoring-reports.md)
  
[Uso dei report di monitoraggio in Skype for Business Server](../../manage/health-and-monitoring/monitoring-reports.md)
