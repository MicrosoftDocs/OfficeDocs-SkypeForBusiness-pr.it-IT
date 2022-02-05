---
title: CLS Logger per Skype for Business Server 2015
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/25/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 1eaf8cdf-3dcd-4d6e-ae68-b6f6f9431ad8
description: 'Riepilogo: informazioni su come utilizzare il Logger del servizio di registrazione centralizzata (CLS) in Skype for Business Server 2015.'
---

# <a name="cls-logger-for-skype-for-business-server-2015"></a>CLS Logger per Skype for Business Server 2015
 
**Riepilogo:** Informazioni su come usare il Logger del servizio di registrazione centralizzata (CLS) in Skype for Business Server 2015.
  
ClS Logger è uno strumento che consente di gestire i registri generati dal servizio di registrazione centralizzata.
  
## <a name="prerequisites"></a>Prerequisiti

Per utilizzare correttamente cls Logger, è necessario verificare che siano vere le condizioni seguenti:
  
- Lo strumento viene utilizzato in un computer membro del dominio in cui è in esecuzione il servizio di registrazione centralizzata (CLS). Lo strumento non è attualmente supportato nelle sessioni remote di PowerShell.
    
- Il file Default.tmx dalla cartella di traccia (la cartella in cui vengono acquisiti i dati di traccia per CLS) e Snooper deve essere copiato nella stessa cartella in cui è installato lo strumento CLS Logger.
    
## <a name="check-the-logging-status-of-a-set-of-poolscomputers"></a>Controllare lo stato di registrazione di un set di pool/computer

Utilizzare i comandi seguenti per controllare lo stato della registrazione:
  
1. Nella scheda "Scenari di avvio/arresto" selezionare un raggruppamento di pool e/o computer nella visualizzazione albero della topologia.
    
2. Fare clic sul pulsante Stato registrazione.
    
3. Visualizzare l'output del comando nell'area Output comando di PowerShell per informazioni specifiche sullo stato di registrazione dei pool e/o dei computer selezionati.
    
## <a name="start-an-existing-scenario"></a>Avviare uno scenario esistente

Per avviare uno scenario esistente:
  
1. Nella scheda "Start/Stop Scenarios" seleziona uno scenario esistente dal menu a discesa Scenarios.
    
2. Selezionare un raggruppamento di pool e/o computer nella visualizzazione albero della topologia.
    
3. Fai clic sul pulsante Avvia scenario. L'interfaccia utente verrà disabilitata fino al completamento dell'operazione. Potrebbe essere lento nelle distribuzioni di grandi dimensioni.
    
4. L'interfaccia utente verrà nuovamente abilitata dopo l'avvio dello scenario, i dettagli dell'azione verranno visualizzati anche nell'area Output comandi di PowerShell.
    
5. L'attività potrebbe richiedere del tempo prima che la registrazione venga prelevata da CLS prima di qualsiasi nuovo dato di questo scenario.
    
## <a name="stop-an-existing-scenario"></a>Arrestare uno scenario esistente

Per arrestare uno scenario esistente:
  
1. Nella scheda "Start/Stop Scenarios" seleziona uno scenario esistente dal menu a discesa Scenarios.
    
2. Selezionare un raggruppamento di pool e/o computer nella visualizzazione albero della topologia.
    
3. Fare clic sul pulsante Interrompi scenario. L'interfaccia utente verrà disabilitata fino al completamento dell'operazione. Potrebbe essere lento nelle distribuzioni di grandi dimensioni.
    
4. L'interfaccia utente verrà nuovamente abilitata dopo l'arresto dello scenario, i dettagli dell'azione verranno visualizzati anche nell'area Output comandi di PowerShell.
    
![Avvio e arresto del logger CLS.](../../media/2c4a36c2-b5db-4550-a3b3-41f18e0e2f0c.png)
  
## <a name="search-for-logs"></a>Cercare log

Per cercare i log, selezionare la scheda "Cerca log CLS" e fare clic sul pulsante "Cerca log" dopo aver compilato i campi visualizzati come descritto di seguito:
  
> **Cartella file di registro** Cartella in cui salvare i risultati della ricerca nei log. (Obbligatorio)
> 
> **Livello di registrazione** Questo determina il livello più basso che verrà visualizzato nei risultati. Ad esempio, se è selezionata l'opzione Avviso, verranno visualizzati solo Avviso, Errore e Errore irreversibile. Il valore predefinito è Debug.
> 
> **Pool** Pool di computer su cui eseguire la ricerca nei log, questi sono i nodi padre della visualizzazione albero. (Obbligatorio)
> 
> **Computer** Singoli computer in cui eseguire la ricerca nei log, si tratta di tutti i nodi figlio nella visualizzazione albero. (Obbligatorio)
> 
> **Ora inizio** Periodo di tempo da cui CLS esegue una query nei log. (Obbligatorio)
> 
> **Ora fine** Periodo di tempo in cui CLS interromperà l'esecuzione di query nei log. (Obbligatorio)
> 
> **Componenti** Consente di selezionare i componenti da aggiungere alla query. (Facoltativa)
> 
> **ID chiamata** ID chiamata di tutte le finestre di dialogo SIP in base a cui filtrare. Si noti che questo campo utilizza la corrispondenza esatta. (Facoltativa)
> 
> **ID conferenza** ID conferenza di tutte le conferenze in base a cui filtrare. Si noti che questo campo utilizza la corrispondenza esatta. (Facoltativa)
> 
> **Indirizzo IP** L'indirizzo IP in base a cui filtrare. Si noti che questo campo utilizza la corrispondenza esatta. (Facoltativa)
> 
> **ID correlazione** Istruzioni di traccia collegate logicamente tra loro da questo ID. (Facoltativa)
> 
> **Telefono Numero filtro** per numero di telefono. (Facoltativa)
> 
> **URI SIP** Filtra in base all'URI SIP. (Facoltativa)
> 
> **Contenuto del messaggio SIP contiene** Filtra in base al contenuto del messaggio SIP, in questo campo verrà ricercata sottostringa. (Facoltativa)
> 
> **Match Any** Esegue la ricerca utilizzando un or logico, se selezionato. Il valore predefinito è Corrispondenza esatta di tutti i parametri.
> 
> **Ignora registri di rete** Se selezionata, la ricerca nei registri di rete viene ignorata.
    
![Log di ricerca di CLS Logger.](../../media/5793ea3c-6f5f-40ef-8b53-100da831eedf.png)
  
## <a name="create-a-scenario"></a>Creare uno scenario

1. Nella scheda **Modifica scenari** fare clic sul **pulsante Crea** scenario.
    
    > [!NOTE]
    > La creazione di un nuovo scenario clona la configurazione dello scenario attualmente selezionato. Se si fa **clic su Impostazioni** prima di creare un nuovo scenario, verrà avviato senza componenti e contrassegni selezionati.
  
2. Immettere il nome dello scenario che si desidera creare e premere INVIO oppure fare clic sul pulsante OK.
    
3. Il nuovo scenario verrà creato. Al completamento della creazione, l'elenco a discesa Scenari verrà selezionato con lo scenario appena creato.
    
## <a name="modify-a-scenario"></a>Modificare uno scenario

![Cattura di schermata del logger CLS, modifica degli scenari.](../../media/abbbcac0-8a2e-48af-a22f-4fee0283a29f.png)
  
1. Nella scheda **Modifica scenari** individuare lo scenario desiderato da modificare.
    
2. Apportare le modifiche desiderate ai componenti, ai livelli e ai contrassegni.
    
3. Fare clic **sul pulsante Salva** scenario.
    
4. Dopo aver salvato correttamente lo scenario, il riquadro delle informazioni sullo scenario verrà aggiornato con la configurazione aggiornata.
    
## <a name="delete-a-scenario"></a>Eliminare uno scenario

1. Nella scheda **Modifica scenari** selezionare uno scenario esistente dal menu a discesa Scenari.
    
2. Fare **clic su Elimina** scenario per eliminare lo scenario.
    
3. Dopo aver confermato l'azione, lo scenario verrà eliminato.
    

