---
title: Compatibilità con Skype for business con le app di Office
ms.author: v-lanac
author: lanachin
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ac3a1046-b438-4e21-9d4f-3b0057dd685d
description: Informazioni sui modi in cui è possibile accedere alle funzionalità di Skype for business da Outlook e altre applicazioni di Microsoft Office.
ms.openlocfilehash: c24c6b08e21db357d52b1cc130e53f23b6123ff6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187898"
---
# <a name="skype-for-business-compatibility-with-office-apps"></a>Compatibilità con Skype for business con le app di Office
 
Informazioni sui modi in cui è possibile accedere alle funzionalità di Skype for business da Outlook e altre applicazioni di Microsoft Office.
  
Questo argomento descrive la compatibilità di Skype for business con varie versioni di Microsoft Office Suites. 
  
## <a name="office-and-skype-for-business"></a>Office e Skype for business

La tabella seguente descrive le caratteristiche di Skype for business supportate da diverse versioni di Office una volta che Exchange è distribuito e integrato come descritto in [integrare Skype for Business Server con Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).
  
**Compatibilità con Skype for business e Microsoft Office**

|**Funzionalità**|**Microsoft Office 2010**|**Microsoft Office 2013, 2015 e 2016**|&#x2776; **di Office 2016 per Mac** |
|:-----|:-----|:-----|:-----|
|**Caratteristiche di Outlook** ||||
|Personalizzare gli inviti alle riunioni di Outlook (Aggiungi logo, URL della guida, Disclaimer, testo del piè di pagina)  |No  |Sì   |Supporto per più paesi|
|Configurare l'opzione riunione per disattivare l'audio e il video dei partecipanti per impostazione predefinita    |No    |Sì    |No    |
|Archivio contatti unificato per la gestione degli elenchi di contatti in Office e Skype for business    |No    |Sì (richiede Exchange 2013 o versione successiva)    |Sì    |
|Immagini del profilo ad alta risoluzione    |No    |Sì (richiede Exchange 2013 o versione successiva)    |Sì    |
|Stato presenza nei campi Microsoft Outlook da, a e CC    |Sì    |Supporto per più paesi    |Supporto per più paesi    |
|Rispondere con un messaggio istantaneo o una chiamata dal menu disponibilità    |Sì (dalla scheda contatto)    |Sì (dalla scheda contatto)    |Sì (dalla scheda contatto)    |
|Stato presenza in una convocazione di riunione nella scheda Assistente pianificazione    |Sì    |Sì    |No    |
|Rispondere con messaggi ISTANTANEi o chiamate dalla barra degli strumenti o dalla barra multifunzione in un messaggio di posta elettronica ricevuto    |Sì    |Supporto per più paesi    |Supporto per più paesi    |
|**Altre app di Office**   ||||
|Note condivise di OneNote    |No    |Sì    |No    |
|Configurazione integrata nel programma di installazione di Office    |No    |Sì    |No    |
|Contenuto della presentazione di PowerPoint    |Sì    |Sì (VBSS disponibile anche)    |Sì    |
|Messaggistica istantanea e presenza nei file di Microsoft Word e Microsoft Excel (smart tag abilitati)    |Solo Microsoft Word    |Solo Microsoft Word    |No    |
|Messaggistica istantanea e presenza nei siti di Microsoft SharePoint (Outlook deve essere installato)    |Sì    |Sì    |No    |
   
&#x2776;: presuppone che tu abbia installato e sia attualmente in uso un client Skype for business su Mac o il client Lync 2011 per Mac.
  
## <a name="exchange-server-and-skype-for-business"></a>Exchange Server e Skype for business

La tabella seguente descrive il supporto di Skype for business per varie versioni di Exchange Server. Outlook deve essere installato nel computer client per gestire chiamate MAPI estese e alcune funzionalità richiedono l'uso di servizi Web Exchange (EWS).
  
**Compatibilità con Skype for business e Exchange Server**

|**Versione di Exchange Server**|**Supporto di Skype for business**|
|:-----|:-----|
|Exchange Server 2019 (solo Skype for Business Server 2019) |Uguale al supporto di Exchange Server 2013    |
|Exchange Server 2016    |Uguale al supporto di Exchange Server 2013  <br/> |
|Exchange Server 2013  <br/> |Uguale al supporto di Exchange Server 2010, con l'aggiunta di  <br/>&bull;&nbsp;&nbsp;Archivio contatti unificato  <br/>&bull;&nbsp;&nbsp;Immagini ad alta risoluzione  <br/>&bull;&nbsp;&nbsp;Integrazione di archiviazione  <br/> **Nota:** Per informazioni dettagliate, vedere [integrare Skype for Business Server con Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).  <br/> |
|Exchange Server 2010  <br/>(Solo per Skype for Business Server 2015) |Le caratteristiche seguenti sono disponibili solo tramite EWS:  <br/>&bull;&nbsp;&nbsp;Leggere o eliminare elementi nella cartella Cronologia conversazioni  <br/>&bull;&nbsp;&nbsp;Leggere o eliminare elementi della segreteria telefonica  <br/>&bull;&nbsp;&nbsp;Visualizzare le informazioni di disponibilità estese e l'oggetto e la posizione della riunione  <br/>&bull;&nbsp;&nbsp;Sincronizzazione dei contatti di Exchange  <br/> Le cartelle pubbliche sono facoltative in Exchange Server 2010.  <br/> |
   
## <a name="see-also"></a>Vedere anche
 
[Requisiti del client Windows e supporto software](windows-requirements.md)
  
[Pianificare i client delle riunioni (app Web e riunioni)](meetings-clients.md)

