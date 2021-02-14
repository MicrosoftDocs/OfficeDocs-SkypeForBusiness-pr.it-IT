---
title: Compatibilità di Skype for Business con le app di Office
ms.author: v-cichur
author: cichur
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ac3a1046-b438-4e21-9d4f-3b0057dd685d
description: Comprendere i modi in cui è possibile accedere alle funzionalità di Skype for Business da Outlook e altre Microsoft Office applicazioni.
ms.openlocfilehash: b3d792d5e6376e4d845aa74f0585acf7d9a70d81
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802736"
---
# <a name="skype-for-business-compatibility-with-office-apps"></a>Compatibilità di Skype for Business con le app di Office
 
Comprendere i modi in cui è possibile accedere alle funzionalità di Skype for Business da Outlook e altre Microsoft Office applicazioni.
  
In questo argomento viene descritta la compatibilità di Skype for Business con varie versioni Microsoft Office suite. 
  
## <a name="office-and-skype-for-business"></a>Office e Skype for Business

Nella tabella seguente vengono descritte le funzionalità di Skype for Business supportate da varie versioni di Office dopo la distribuzione e l'integrazione di Exchange, come descritto in Integrare [Skype for Business Server con Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).
  
**Compatibilità di Skype for Business e Microsoft Office**

|**Caratteristica**|**Microsoft Office 2010**|**Microsoft Office 2013, 2015 e 2016**|**Office 2016 per Mac** &#x2776; |
|:-----|:-----|:-----|:-----|
|**Caratteristiche di Outlook** ||||
|Personalizzare gli inviti alle riunioni di Outlook (aggiungere il logo, l'URL della Guida, la dichiarazione di non responsabilità, il testo del piè di pagina)  |No  |Sì   |Sì|
|Configurare l'opzione di riunione per disattivare l'audio e il video dei partecipanti per impostazione predefinita    |No    |Sì    |No    |
|Archivio contatti unificato per la gestione degli elenchi contatti in Office e Skype for Business    |No    |Sì (richiede Exchange 2013 o versione successiva)    |Sì    |
|Immagini di profilo ad alta risoluzione    |No    |Sì (richiede Exchange 2013 o versione successiva)    |Sì    |
|Stato presenza nei campi Da, A e Cc di Microsoft Outlook    |Sì    |Sì    |Sì    |
|Rispondere con messaggistica istantanea o chiamata dal menu disponibilità    |Sì (dalla scheda contatto)    |Sì (dalla scheda contatto)    |Sì (dalla scheda contatto)    |
|Stato presenza in una convocazione di riunione nella scheda Assistente Pianificazione    |Sì    |Sì    |No    |
|Rispondere con messaggistica istantanea o chiamata dalla barra degli strumenti o dalla barra multifunzione in un messaggio di posta elettronica ricevuto    |Sì    |Sì    |Sì    |
|**Altre app di Office**   ||||
|Note condivise di OneNote    |No    |Sì    |No    |
|Installazione integrata nel programma di installazione di Office    |No    |Sì    |No    |
|Contenuto della presentazione di PowerPoint    |Sì    |Sì (vbss disponibile anche)    |Sì    |
|Messaggistica istantanea e presenza nei file di Microsoft Word e Microsoft Excel (smart tag abilitati)    |Solo Microsoft Word    |Solo Microsoft Word    |No    |
|Messaggistica istantanea e presenza nei siti di Microsoft SharePoint (è necessario che Outlook sia installato)    |Sì    |Sì    |No    |
   
&#x2776; - Presuppone che tu abbia installato e attualmente in esecuzione un client Skype for Business su Mac o il client Lync 2011 per Mac.
  
## <a name="exchange-server-and-skype-for-business"></a>Exchange Server e Skype for Business

Nella tabella seguente viene descritto il supporto di Skype for Business per varie versioni di Exchange Server. Per gestire le chiamate MAPI estese, è necessario che nel client sia installato Office Outlook e alcune funzionalità richiedono l'utilizzo di Servizi Web Exchange.
  
**Skype for Business e Exchange Server Compatibilità**

|**Versione di Exchange Server**|**Supporto di Skype for Business**|
|:-----|:-----|
|Exchange Server 2019 (solo Skype for Business Server 2019) |Uguale al Exchange Server 2013    |
|Exchange Server 2016    |Uguale al Exchange Server 2013  <br/> |
|Exchange Server 2013  <br/> |Uguale al Exchange Server 2010, con l'aggiunta di  <br/>&bull;&nbsp;&nbsp;Archivio contatti unificato  <br/>&bull;&nbsp;&nbsp;Immagini ad alta risoluzione  <br/>&bull;&nbsp;&nbsp;Integrazione dell'archiviazione  <br/> **Nota:** Per informazioni dettagliate, [vedere Integrare Skype for Business Server con Exchange Server.](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)  <br/> |
|Exchange Server 2010  <br/>(solo Skype for Business Server 2015) |Le funzionalità seguenti sono disponibili solo tramite i Servizi Web Exchange:  <br/>&bull;&nbsp;&nbsp;Lettura o eliminazione di elementi nella cartella Cronologia conversazioni  <br/>&bull;&nbsp;&nbsp;Lettura o eliminazione di elementi del sistema di caselle vocali  <br/>&bull;&nbsp;&nbsp;Visualizzare le informazioni sulla disponibilità estese e l'oggetto e la posizione della riunione  <br/>&bull;&nbsp;&nbsp;Sincronizzazione dei contatti di Exchange  <br/> Le cartelle pubbliche sono facoltative Exchange Server 2010.  <br/> |
   
## <a name="see-also"></a>Vedere anche
 
[Requisiti client Windows e supporto software](windows-requirements.md)
  
[Pianificare i client riunioni (app Web e app Riunioni)](meetings-clients.md)

