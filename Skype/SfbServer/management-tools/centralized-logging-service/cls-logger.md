---
title: CLS Logger per Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/25/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1eaf8cdf-3dcd-4d6e-ae68-b6f6f9431ad8
description: 'Riepilogo: informazioni su come usare il logger di servizi di registrazione centralizzato in Skype for Business Server 2015.'
ms.openlocfilehash: 496f30bdcedeb491bd5bfa211f08c04853b49bf8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36186827"
---
# <a name="cls-logger-for-skype-for-business-server-2015"></a>CLS Logger per Skype for Business Server
 
**Riepilogo:** Informazioni su come usare il logger di servizi di registrazione centralizzato in Skype for Business Server 2015.
  
Il logger CLS è uno strumento che consente di gestire i registri generati dal servizio di registrazione centralizzato.
  
## <a name="prerequisites"></a>Prerequisiti

Per usare correttamente il logger CLS, è necessario verificare che le condizioni seguenti siano vere:
  
- Si usa lo strumento in un computer che fa parte del dominio in cui è in uso il servizio di registrazione centralizzato (CLS). Lo strumento non è attualmente supportato nelle sessioni remote di PowerShell.
    
- Il file default. TMX dalla cartella di traccia (la cartella in cui vengono acquisiti i dati di traccia per CLS) e Snooper deve essere copiato nella stessa cartella in cui è installato lo strumento del logger CLS.
    
## <a name="check-the-logging-status-of-a-set-of-poolscomputers"></a>Controllare lo stato di registrazione di un set di pool/computer

Usare i comandi seguenti per controllare lo stato della registrazione:
  
1. Nella scheda "scenari di avvio/arresto" selezionare un raggruppamento di pool e/o computer nella visualizzazione ad albero della topologia.
    
2. Fare clic sul pulsante stato registrazione.
    
3. Visualizzare l'output del comando nell'area di output del comando di PowerShell per informazioni specifiche sullo stato di registrazione dei pool e/o computer selezionati.
    
## <a name="start-an-existing-scenario"></a>Avviare uno scenario esistente

Per avviare uno scenario esistente:
  
1. Nella scheda "scenari di avvio/arresto" selezionare uno scenario esistente nel menu a discesa scenari.
    
2. Selezionare un raggruppamento di pool e/o computer nella visualizzazione ad albero della topologia.
    
3. Fare clic sul pulsante Start scenario. L'interfaccia utente viene disabilitata fino al completamento dell'operazione. Questa operazione può essere lenta per le distribuzioni di grandi dimensioni.
    
4. L'interfaccia utente verrà abilitata di nuovo quando lo scenario è stato avviato correttamente, anche i dettagli dell'azione verranno visualizzati nell'area di output del comando di PowerShell.
    
5. L'attività può richiedere un po' di tempo prima che la registrazione venga rilevata da CLS prima di qualsiasi nuovo dato da questo scenario.
    
## <a name="stop-an-existing-scenario"></a>Arrestare uno scenario esistente

Per interrompere uno scenario esistente:
  
1. Nella scheda "scenari di avvio/arresto" selezionare uno scenario esistente nel menu a discesa scenari.
    
2. Selezionare un raggruppamento di pool e/o computer nella visualizzazione ad albero della topologia.
    
3. Fare clic sul pulsante Interrompi scenario. L'interfaccia utente viene disabilitata fino al completamento dell'operazione. Questa operazione può essere lenta per le distribuzioni di grandi dimensioni.
    
4. L'interfaccia utente verrà abilitata nuovamente dopo l'interruzione dello scenario, anche i dettagli dell'azione verranno visualizzati nell'area di output del comando di PowerShell.
    
![Avvio e arresto del logger CLS](../../media/2c4a36c2-b5db-4550-a3b3-41f18e0e2f0c.png)
  
## <a name="search-for-logs"></a>Cercare log

Per cercare i log, selezionare la scheda "Cerca registri CLS" e fare clic sul pulsante "Cerca log" dopo aver compilato i campi visualizzati come descritto di seguito:
  
> **Cartella file di log** Cartella in cui salvare i risultati della ricerca nel log. Necessaria
> 
> **Livello di log** Questo determina il livello più basso che verrà visualizzato nei risultati. Ad esempio, se è selezionato avviso, verranno visualizzati solo gli avvisi, gli errori e i fatali. Impostazioni predefinite per il debug.
> 
> **Pool** Pool di computer in cui eseguire la ricerca del log, questi sono i nodi padre della visualizzazione albero. Necessaria
> 
> **Computer** Singoli computer per cui eseguire la ricerca del log, questi sono tutti i nodi figlio nella visualizzazione albero. Necessaria
> 
> **Ora di inizio** Il periodo di tempo in cui CLS eseguirà una query sui log. Necessaria
> 
> **Ora di fine** Il periodo di tempo in cui CLS smetterà di eseguire query sui log. Necessaria
> 
> **Componenti** Usato per selezionare i componenti da aggiungere alla query. Opzionale
> 
> **ID chiamata** ID chiamata di tutte le finestre di dialogo SIP da filtrare. Nota, questo campo Usa la corrispondenza esatta. Opzionale
> 
> **ID conferenza** ID conferenza di tutte le conferenze a cui applicare il filtro. Nota, questo campo Usa la corrispondenza esatta. Opzionale
> 
> **Indirizzo IP** Indirizzo IP che deve essere filtrato. Nota, questo campo Usa la corrispondenza esatta. Opzionale
> 
> **ID** di correlazione Istruzioni di analisi collegate logicamente tra loro da questo ID. Opzionale
> 
> **Numero di telefono** Filtrare in base al numero di telefono. Opzionale
> 
> **URI SIP** Filtrare in base all'URI SIP. Opzionale
> 
> **Contenuto del messaggio SIP contiene** Filtrare in base al contenuto del messaggio SIP, la ricerca substringa verrà racchiusa in questo campo. Opzionale
> 
> **Corrispondere a qualsiasi** Esegue la ricerca usando un controllo logico o se selezionato. Impostazione predefinita per la corrispondenza esatta di tutti i parametri.
> 
> **Ignorare i registri di rete** Ignora la ricerca di eventuali log di rete se selezionata.
    
![Log di ricerca nel logger CLS](../../media/5793ea3c-6f5f-40ef-8b53-100da831eedf.png)
  
## <a name="create-a-scenario"></a>Creare uno scenario

1. Nella scheda **Modifica scenari** fare clic sul pulsante **Crea scenario** .
    
    > [!NOTE]
    > La creazione di un nuovo scenario clona la configurazione dello scenario attualmente selezionato. Se si fa clic su **Cancella impostazioni** prima di creare un nuovo scenario, inizierà senza componenti e contrassegni selezionati.
  
2. Immettere il nome dello scenario da creare e premere INVIO o fare clic sul pulsante OK.
    
3. Verrà ora creato il nuovo scenario. Dopo aver completato la creazione, l'elenco a discesa degli scenari verrà selezionato con lo scenario appena creato.
    
## <a name="modify-a-scenario"></a>Modificare uno scenario

![Screenshot del logger CLS, scenari di modifica](../../media/abbbcac0-8a2e-48af-a22f-4fee0283a29f.png)
  
1. Nella scheda **Modifica scenari** individuare lo scenario desiderato per la modifica.
    
2. Apportare le modifiche desiderate ai componenti, ai livelli e ai contrassegni.
    
3. Fare clic sul pulsante **Salva scenario** .
    
4. Dopo aver salvato correttamente lo scenario, il riquadro informazioni scenario verrà aggiornato con la configurazione aggiornata.
    
## <a name="delete-a-scenario"></a>Eliminare uno scenario

1. Nella scheda **Modifica scenari** selezionare uno scenario esistente nel menu a discesa scenari.
    
2. Fare clic su **Elimina scenario** per eliminare lo scenario.
    
3. Dopo aver confermato l'azione, lo scenario verrà eliminato.
    

