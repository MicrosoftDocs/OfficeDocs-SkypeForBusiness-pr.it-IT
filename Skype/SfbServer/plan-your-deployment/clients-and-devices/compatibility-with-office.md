---
title: Skype for Business compatibilità con Office app
ms.author: v-mahoffman
author: HowlinWolf-92
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ac3a1046-b438-4e21-9d4f-3b0057dd685d
description: Comprendere i modi in cui è possibile accedere Skype for Business funzionalità da Outlook altre Microsoft Office applicazioni.
ms.openlocfilehash: 06a019416ad8d32b0234b08c01b09630dd07a2ef
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60862133"
---
# <a name="skype-for-business-compatibility-with-office-apps"></a>Skype for Business compatibilità con Office app
 
Comprendere i modi in cui è possibile accedere Skype for Business funzionalità da Outlook altre Microsoft Office applicazioni.
  
In questo argomento viene descritta la compatibilità di Skype for Business con diverse versioni di Microsoft Office suite. 
  
## <a name="office-and-skype-for-business"></a>Office e Skype for Business

Nella tabella seguente vengono descritte le funzionalità di Skype for Business supportate da diverse versioni di Office dopo la distribuzione e l'integrazione di Exchange, come descritto in [Integrare Skype for Business Server con Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).
  
**Skype for Business e Microsoft Office compatibilità**

|**Funzionalità**|**Microsoft Office 2010**|**Microsoft Office 2013, 2015 e 2016**|**Office 2016 per Mac** &#x2776; |
|:-----|:-----|:-----|:-----|
|**Outlook funzionalità** ||||
|Personalizzare Outlook convocazioni di riunione (aggiungere logo, URL guida, dichiarazione di non responsabilità, testo piè di pagina)  |No  |Sì   |Sì|
|Opzione Configura riunione per disattivare audio e video dei partecipanti per impostazione predefinita    |No    |Sì    |No    |
|Archivio contatti unificato per la gestione degli elenchi contatti Office e Skype for Business    |No    |Sì (richiede Exchange 2013 o versione successiva)    |Sì    |
|Immagini di profilo ad alta risoluzione    |No    |Sì (richiede Exchange 2013 o versione successiva)    |Sì    |
|Stato presenza nei campi Microsoft Outlook Da, A e Cc    |Sì    |Sì    |Sì    |
|Rispondi con messaggistica istantanea o chiamata dal menu disponibilità    |Sì (dalla scheda contatto)    |Sì (dalla scheda contatto)    |Sì (dalla scheda contatto)    |
|Stato presenza in una convocazione di riunione nella scheda Assistente Pianificazione    |Sì    |Sì    |No    |
|Rispondere con messaggistica istantanea o chiamata dalla barra degli strumenti o dalla barra multifunzione in un messaggio di posta elettronica ricevuto    |Sì    |Sì    |Sì    |
|**Altre Office app**   ||||
|OneNote note condivise    |No    |Sì    |No    |
|Installazione integrata nel programma di Office di installazione    |No    |Sì    |No    |
|PowerPoint contenuto della presentazione    |Sì    |Sì (disponibile anche VBSS)    |Sì    |
|Messaggistica istantanea e presenza nei file di Microsoft Word e Microsoft Excel (smart tag abilitati)    |Solo Microsoft Word    |Solo Microsoft Word    |No    |
|Messaggistica istantanea e presenza nei siti di Microsoft SharePoint (è necessario che Outlook sia installato)    |Sì    |Sì    |No    |
   
&#x2776; - Si presuppone che sia stato installato e attualmente in esecuzione un Skype for Business nel client Mac o nel client Lync 2011 per Mac.
  
## <a name="exchange-server-and-skype-for-business"></a>Exchange Server e Skype for Business

Nella tabella seguente viene descritto Skype for Business supporto per diverse versioni di Exchange Server. Per gestire le chiamate MAPI estese, è necessario che nel client sia installato Office Outlook e alcune funzionalità richiedono l'utilizzo di Servizi Web Exchange.
  
**Skype for Business e Exchange Server compatibilità**

|**Versione di Exchange Server**|**Skype for Business supporto**|
|:-----|:-----|
|Exchange Server 2019 (solo Skype for Business Server 2019) |Come nel Exchange Server 2013    |
|Exchange Server 2016    |Come nel Exchange Server 2013  <br/> |
|Exchange Server 2013  <br/> |Come il Exchange Server 2010, con l'aggiunta di  <br/>&bull;&nbsp;&nbsp;Archivio contatti unificato  <br/>&bull;&nbsp;&nbsp;Immagini ad alta risoluzione  <br/>&bull;&nbsp;&nbsp;Integrazione dell'archiviazione  <br/> **Nota:** Per informazioni dettagliate, vedere [Integrate Skype for Business Server with Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).  <br/> |
|Exchange Server 2010  <br/>(Skype for Business Server solo 2015) |Le funzionalità seguenti sono disponibili solo tramite i Servizi Web Exchange:  <br/>&bull;&nbsp;&nbsp;Lettura o eliminazione di elementi nella cartella Cronologia conversazioni  <br/>&bull;&nbsp;&nbsp;Lettura o eliminazione di elementi del sistema di caselle vocali  <br/>&bull;&nbsp;&nbsp;Visualizzare le informazioni sulla disponibilità estese e l'oggetto e la posizione della riunione  <br/>&bull;&nbsp;&nbsp;Exchange sincronizzazione dei contatti  <br/> Le cartelle pubbliche sono facoltative Exchange Server 2010.  <br/> |
   
## <a name="see-also"></a>Vedere anche
 
[Windows client e supporto software](windows-requirements.md)
  
[Pianificare i client riunioni (App Web e app Riunioni)](meetings-clients.md)

