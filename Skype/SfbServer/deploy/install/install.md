---
title: Installare Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/14/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 71299b34-8783-4384-9949-0d3162c8a36e
description: "Riepilogo: informazioni su come preparare l'ambiente per un'installazione di Skype for Business Server. Scaricare una versione di valutazione gratuita Skype for Business Server dal Centro di valutazione Microsoft all'indirizzo: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server ."
ms.openlocfilehash: 9e30a3d91f5aaaf8d1717123ffd59499e96fbd7d
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58609823"
---
# <a name="install-skype-for-business-server"></a>Installare Skype for Business Server
 
**Riepilogo:** Informazioni su come preparare l'ambiente per un'installazione di Skype for Business Server. Scaricare una versione di valutazione gratuita Skype for Business Server dal Centro di valutazione Microsoft all'indirizzo: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server) .
  
In questo articolo viene illustrata un'installazione di esempio di Skype for Business Server. In questo articolo non viene eseguito un tentativo di eseguire tutte le procedure necessarie per eseguire un'installazione Skype for Business Server completa. L'obiettivo è fornire procedure di esempio in una topologia strettamente definita che include funzionalità di base di meet-and-share.
  
## <a name="overview-of-the-install-process-for-skype-for-business-server"></a>Panoramica del processo di installazione per Skype for Business Server

Un'installazione di Skype for Business Server include molte procedure diverse. Le procedure necessarie per eseguire Skype for Business Server nell'ambiente dipendono dalle specifiche dell'ambiente. Ad esempio, se si utilizza Windows Server per DNS, si trarrà vantaggio dalla procedura di esempio per l'aggiunta di una voce DNS. Se si utilizza un altro sistema per DNS, è necessario seguire le procedure per il sistema DNS specifico. Ciò vale per molte delle procedure descritte in questa sezione.
  
Skype for Business Server è disponibile in edizione Standard e edizione Enterprise. La differenza principale è che edizione Standard non supporta le funzionalità di disponibilità elevata incluse in edizione Enterprise. 
  
Skype for Business Server è un prodotto avanzato e il processo di installazione esatto dipende molto dalle circostanze specifiche. In questa sezione vengono descritti i passaggi generali per installare il prodotto. Tuttavia, ogni procedura potrebbe essere diversa a seconda dell'ambiente e delle decisioni di pianificazione. Ad esempio, per le organizzazioni di piccole dimensioni un singolo server, l'esecuzione di Skype for Business Server edizione Standard potrebbe essere appropriata, mentre un'organizzazione multinazionale di grandi dimensioni potrebbe avere 50 server in posizioni in tutto il mondo dedicate al prodotto.
  
> [!NOTE]
> Per informazioni sugli aggiornamenti cumulativi più recenti, vedere [Updates for Skype for Business Server](https://support.microsoft.com/kb/3061064). Dopo aver installato la patch CU1, un amministratore deve eseguire il  `Update-CsAdminRole` cmdlet. Questo cmdlet è necessario per accedere ai nuovi cmdlet GCP tramite Remote PowerShell.
  
> [!IMPORTANT]
> Le procedure descritte in questa sezione sono un esempio di utilizzo di un insieme ristretto di requisiti e presuppongono che siano già state prese decisioni specifiche. Le procedure effettive che è necessario installare Skype for Business Server saranno probabilmente molto diverse. Utilizzare le procedure descritte in questa sezione solo come esempio e non come guida dettagliata per l'installazione di Skype for Business Server in ogni ambiente. 
  
La Skype for Business Server e l'esecuzione per la prima volta implica otto passaggi principali. È necessario comprendere che le procedure di esempio descritte in questa sezione non sono le uniche procedure necessarie per l'installazione Skype for Business Server. Gli otto passaggi seguenti sono semplicemente esempi che consentono di comprendere meglio il processo complessivo e di ottenere un ambiente di lavoro di base funzionante. È possibile eseguire i passaggi da 1 a 5 in qualsiasi ordine. È tuttavia necessario eseguire i passaggi 6, 7 e 8 nell'ordine e dopo i passaggi da 1 a 5, come illustrato nel diagramma. Gli otto passaggi sono:
  
![Panoramica del processo di installazione.](../../media/b1a59b39-a7f0-4781-ac4d-2dfef7ca3700.png)
  
- [Installare i prerequisiti per Skype for Business Server](install-prerequisites.md) : installare i prerequisiti in tutti i server che costituiscono la Skype for Business Server topologia. Si noti che i prerequisiti non sono gli stessi per tutti i ruoli. Ad esempio, i server che forniscono il ruolo front-end dispongono di un set di prerequisiti e i server che forniscono un ruolo director dispongono di un set diverso di prerequisiti. Per ulteriori dettagli, vedere la documentazione relativa alla pianificazione dei prerequisiti.
    
- [Creare una condivisione file in Skype for Business Server](create-a-file-share.md) : Creare una condivisione file che verrà utilizzata dai server in tutta Skype for Business Server topologia.
    
- [Installare gli strumenti di amministrazione in Skype for Business Server](install-administrative-tools.md) : gli strumenti di amministrazione includono Generatore di topologie e Pannello di controllo. È necessario installare gli strumenti di amministrazione in almeno un server della topologia o in una workstation di gestione a 64 bit che esegue una versione del sistema operativo Windows supportata per Skype for Business Server.
    
- [Preparare Active Directory per Skype for Business Server](prepare-active-directory.md) : Skype for Business Server funziona a stretto contatto con Active Directory. È necessario preparare il dominio di Active Directory per l'utilizzo con Skype for Business Server. È possibile eseguire questa operazione tramite la Distribuzione guidata e viene eseguita una sola volta per il dominio. Questo perché il processo crea gruppi e modifica il dominio ed è necessario farlo una sola volta.
    
- [Creare record DNS per Skype for Business Server](create-dns-records.md) : per Skype for Business Server corretto, è necessario che siano presenti diverse impostazioni DNS. In questo modo i client sanno come accedere ai servizi e i server conoscono l'uno dell'altro. Queste impostazioni devono essere completate una sola volta per ogni distribuzione perché una volta assegnata una voce DNS, questa è disponibile in tutto il dominio.
    
- [Creare e pubblicare](create-and-publish-new-topology.md) una nuova topologia in Skype for Business Server : prima di poter installare il sistema Skype for Business Server in ognuno dei server della topologia, è necessario creare una topologia e pubblicarla. Quando si pubblica una topologia, le informazioni sulla topologia vengono caricate nel database dell'archivio di gestione centrale. Se si tratta di un pool edizione Enterprise, si sta creando il database dell'archivio di gestione centrale la prima volta che si pubblica una nuova topologia. Se si tratta edizione Standard, è necessario eseguire il processo Prepare First edizione Standard Server dalla Distribuzione guidata prima di pubblicare una topologia. In questo modo si prepara edizione Standard'installazione di un'istanza SQL Server Express Edition e la creazione dell'archivio di gestione centrale.
    
- [Installare Skype for Business Server](install-skype-for-business-server.md) nei server della topologia: dopo aver caricato la topologia nell'archivio di gestione centrale e che Active Directory sa quali server eseguiranno i ruoli, è necessario installare il sistema Skype for Business Server in ognuno dei server della topologia.
    
- Verificare la topologia [in Skype for Business Server:](verify-the-topology.md) dopo aver pubblicato la topologia e aver installato i componenti di sistema di Skype for Business Server in ognuno dei server della topologia, è possibile verificare che la topologia funzioni come previsto. Ciò include la verifica che la configurazione sia stata propagata a tutti i server Active Directory in modo che l'intero dominio sappia che Skype for Business è disponibile nel dominio.
    

