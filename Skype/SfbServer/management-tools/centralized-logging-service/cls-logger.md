---
title: CLS Logger per Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/25/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1eaf8cdf-3dcd-4d6e-ae68-b6f6f9431ad8
description: 'Riepilogo: informazioni su come usare il Logger del servizio di registrazione centralizzato (CLS) in Skype for Business Server 2015.'
ms.openlocfilehash: a24cdbffc4b7601d325cd132afb5a7cf137b54f4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49835236"
---
# <a name="cls-logger-for-skype-for-business-server-2015"></a>CLS Logger per Skype for Business Server 2015
 
**Riepilogo:** Informazioni su come usare il Logger del servizio di registrazione centralizzato (CLS) in Skype for Business Server 2015.
  
CLS Logger è uno strumento che consente di gestire i log generati dal servizio di registrazione centralizzato.
  
## <a name="prerequisites"></a>Prerequisiti

Per utilizzare correttamente CLS Logger, è necessario verificare che le condizioni seguenti siano vere:
  
- Lo strumento viene utilizzato in un computer membro del dominio in cui è in esecuzione il servizio di registrazione centralizzata (CLS). Lo strumento non è attualmente supportato nelle sessioni remote di PowerShell.
    
- Il file Default.tmx dalla cartella di traccia (la cartella in cui vengono acquisiti i dati di traccia per CLS) e Snooper devono essere copiati nella stessa cartella in cui è installato lo strumento CLS Logger.
    
## <a name="check-the-logging-status-of-a-set-of-poolscomputers"></a>Controllare lo stato di registrazione di un set di pool/computer

Utilizzare i comandi seguenti per controllare lo stato della registrazione:
  
1. Nella scheda "Start/Stop Scenarios" selezionare un raggruppamento di pool e/o computer nella visualizzazione albero della topologia.
    
2. Fare clic sul pulsante Stato registrazione.
    
3. Visualizzare l'output del comando nell'area Output comando di PowerShell per informazioni specifiche sullo stato di registrazione dei pool e/o dei computer selezionati.
    
## <a name="start-an-existing-scenario"></a>Avviare uno scenario esistente

Per avviare uno scenario esistente:
  
1. Nella scheda "Start/Stop Scenarios" seleziona uno scenario esistente dal menu a discesa Scenarios.
    
2. Selezionare un raggruppamento di pool e/o computer nella visualizzazione albero della topologia.
    
3. Fai clic sul pulsante Avvia scenario. L'interfaccia utente verrà disabilitata fino al completamento dell'operazione. Questo può essere lento nelle distribuzioni di grandi dimensioni.
    
4. L'interfaccia utente verrà ri abilitata una volta avviato correttamente lo scenario, i dettagli dell'azione verranno visualizzati anche nell'area output dei comandi di PowerShell.
    
5. L'attività potrebbe richiedere del tempo prima che la registrazione venga selezionata da CLS prima di qualsiasi nuovo dato di questo scenario.
    
## <a name="stop-an-existing-scenario"></a>Arrestare uno scenario esistente

Per arrestare uno scenario esistente:
  
1. Nella scheda "Start/Stop Scenarios" seleziona uno scenario esistente dal menu a discesa Scenarios.
    
2. Selezionare un raggruppamento di pool e/o computer nella visualizzazione albero della topologia.
    
3. Fare clic sul pulsante Interrompi scenario. L'interfaccia utente verrà disabilitata fino al completamento dell'operazione. Questo può essere lento nelle distribuzioni di grandi dimensioni.
    
4. L'interfaccia utente verrà ri abilitata una volta arrestato lo scenario, i dettagli dell'azione verranno visualizzati anche nell'area output dei comandi di PowerShell.
    
![Avvio e arresto di CLS Logger](../../media/2c4a36c2-b5db-4550-a3b3-41f18e0e2f0c.png)
  
## <a name="search-for-logs"></a>Cercare log

Per cercare i log, selezionare la scheda "Search CLS Logs" e fare clic sul pulsante "Search Logs" dopo aver compilato i campi visualizzati come descritto di seguito:
  
> **Cartella file di registro** Cartella in cui salvare i risultati della ricerca nei log. (Obbligatorio)
> 
> **Livello di registrazione** Questo determina il livello più basso che verrà visualizzato nei risultati. Ad esempio, se è selezionato Avviso, verranno visualizzati solo gli avvisi, gli errori e le errori irreversibili. L'impostazione predefinita è Debug.
> 
> **Pool** Pool di computer in cui eseguire la ricerca nei log, che sono i nodi padre della visualizzazione albero. (Obbligatorio)
> 
> **Computer** Singoli computer in cui eseguire la ricerca nei log, si tratta di tutti i nodi figlio nella visualizzazione albero. (Obbligatorio)
> 
> **Ora di inizio** Periodo di tempo da cui CLS esegue una query nei registri. (Obbligatorio)
> 
> **Ora di fine** Periodo di tempo in cui CLS interromperà l'esecuzione di query nei log. (Obbligatorio)
> 
> **Componenti** Consente di selezionare i componenti da aggiungere alla query. (Facoltativo)
> 
> **ID chiamata** ID chiamata di tutte le finestre di dialogo SIP in base a cui filtrare. Si noti che in questo campo viene utilizzata la corrispondenza esatta. (Facoltativo)
> 
> **ID conferenza** ID conferenza di tutte le conferenze in base a cui filtrare. Si noti che in questo campo viene utilizzata la corrispondenza esatta. (Facoltativo)
> 
> **Indirizzo IP** Indirizzo IP da filtrare. Si noti che in questo campo viene utilizzata la corrispondenza esatta. (Facoltativo)
> 
> **ID correlazione** Istruzioni di traccia collegate logicamente da questo ID. (Facoltativo)
> 
> **Numero di telefono** Filtra in base al numero di telefono. (Facoltativo)
> 
> **URI SIP** Filtra in base all'URI SIP. (Facoltativo)
> 
> **Contenuto del messaggio SIP** Filtra in base al contenuto del messaggio SIP, in questo modo verrà ricercata sottostringhe all'interno di questo campo. (Facoltativo)
> 
> **Corrisponde a qualsiasi** Esegue la ricerca utilizzando un OR logico, se selezionato. L'impostazione predefinita corrisponde esattamente a tutti i parametri.
> 
> **Ignora registri di rete** Se selezionata, la ricerca viene ignorata nei registri di rete.
    
![Log di ricerca di CLS Logger](../../media/5793ea3c-6f5f-40ef-8b53-100da831eedf.png)
  
## <a name="create-a-scenario"></a>Creare uno scenario

1. Nella scheda **Modifica scenari** fare clic sul **pulsante Crea** scenario.
    
    > [!NOTE]
    > La creazione di un nuovo scenario clona la configurazione dello scenario attualmente selezionato. Se si fa **clic su Cancella impostazioni** prima di creare un nuovo scenario, verrà avviato senza componenti e contrassegni selezionati.
  
2. Immettere il nome dello scenario che si desidera creare e premere INVIO o fare clic sul pulsante OK.
    
3. Verrà creato il nuovo scenario. Al momento della creazione, l'elenco a discesa Scenari verrà selezionato con lo scenario appena creato.
    
## <a name="modify-a-scenario"></a>Modificare uno scenario

![Screenshot di CLS Logger, modifica degli scenari](../../media/abbbcac0-8a2e-48af-a22f-4fee0283a29f.png)
  
1. Nella scheda **Modifica scenari** individuare lo scenario desiderato da modificare.
    
2. Apportare le modifiche desiderate ai componenti, ai livelli e ai flag.
    
3. Fare clic **sul pulsante Salva** scenario.
    
4. Dopo aver salvato correttamente lo scenario, il riquadro delle informazioni sullo scenario verrà aggiornato con la configurazione aggiornata.
    
## <a name="delete-a-scenario"></a>Eliminare uno scenario

1. Nella scheda **Modifica scenari** selezionare uno scenario esistente dal menu a discesa Scenari.
    
2. Fare **clic su Elimina scenario** per eliminare lo scenario.
    
3. Dopo aver confermato l'azione, lo scenario verrà eliminato.
    

