---
title: Compatibilità di Skype for business con le app di Office
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
description: Comprendere i modi in cui è possibile accedere alle funzionalità di Skype for business da Outlook e altre applicazioni di Microsoft Office.
ms.openlocfilehash: b3d792d5e6376e4d845aa74f0585acf7d9a70d81
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802736"
---
# <a name="skype-for-business-compatibility-with-office-apps"></a>Compatibilità di Skype for business con le app di Office
 
Comprendere i modi in cui è possibile accedere alle funzionalità di Skype for business da Outlook e altre applicazioni di Microsoft Office.
  
In questo argomento viene descritta la compatibilità di Skype for business con diverse versioni di Microsoft Office Suites. 
  
## <a name="office-and-skype-for-business"></a>Office e Skype for business

Nella tabella seguente vengono descritte le funzionalità di Skype for business supportate da diverse versioni di Office dopo la distribuzione e l'integrazione di Exchange, come descritto in [integrazione di Skype for Business Server con Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).
  
**Compatibilità di Skype for business e Microsoft Office**

|**Caratteristica**|**Microsoft Office 2010**|**Microsoft Office 2013, 2015 e 2016**|&#x2776; **di Office 2016 per Mac** |
|:-----|:-----|:-----|:-----|
|**Funzionalità di Outlook** ||||
|Personalizzare gli inviti alle riunioni di Outlook (Aggiungi logo, URL della guida, dichiarazione di non responsabilità, testo del piè di pagina)  |No  |Sì   |Sì|
|Configurare l'opzione riunione per disattivare l'audio e il video dei partecipanti per impostazione predefinita    |No    |Sì    |No    |
|Archivio contatti unificato per la gestione degli elenchi di contatti in Office e Skype for business    |No    |Sì (richiede Exchange 2013 o versione successiva)    |Sì    |
|Immagini del profilo ad alta risoluzione    |No    |Sì (richiede Exchange 2013 o versione successiva)    |Sì    |
|Stato presenza nei campi da, a e CC di Microsoft Outlook    |Sì    |Sì    |Sì    |
|Rispondi con messaggistica istantanea o chiamata dal menu disponibilità    |Sì (dalla scheda contatto)    |Sì (dalla scheda contatto)    |Sì (dalla scheda contatto)    |
|Stato presenza in una convocazione di riunione nella scheda Assistente Pianificazione    |Sì    |Sì    |No    |
|Risposta con messaggistica istantanea o chiamata dalla barra degli strumenti o dalla barra multifunzione in un messaggio di posta elettronica ricevuto    |Sì    |Sì    |Sì    |
|**Altre app di Office**   ||||
|OneNote Shared Notes    |No    |Sì    |No    |
|Installazione integrata nel programma di installazione di Office    |No    |Sì    |No    |
|Contenuto presentazione di PowerPoint    |Sì    |Sì (VBSS disponibile anche)    |Sì    |
|Messaggistica istantanea e presenza nei file di Microsoft Word e Microsoft Excel (smart tag abilitati)    |Solo Microsoft Word    |Solo Microsoft Word    |No    |
|Messaggistica istantanea e presenza nei siti di Microsoft SharePoint (è necessario che Outlook sia installato)    |Sì    |Sì    |No    |
   
&#x2776;-si presuppone che sia stato installato e che attualmente esegua un client Skype for business su Mac o il client Lync 2011 per Mac.
  
## <a name="exchange-server-and-skype-for-business"></a>Exchange Server e Skype for business

Nella tabella seguente viene descritto il supporto di Skype for business per diverse versioni di Exchange Server. Per gestire le chiamate MAPI estese, è necessario che nel client sia installato Office Outlook e alcune funzionalità richiedono l'utilizzo di Servizi Web Exchange.
  
**Compatibilità di Skype for business e Exchange Server**

|**Versione di Exchange Server**|**Supporto per Skype for business**|
|:-----|:-----|
|Exchange Server 2019 (solo per Skype for Business Server 2019) |Analogo al supporto di Exchange Server 2013    |
|Exchange Server 2016    |Analogo al supporto di Exchange Server 2013  <br/> |
|Exchange Server 2013  <br/> |Come il supporto di Exchange Server 2010, con l'aggiunta di  <br/>&bull;&nbsp;&nbsp;Archivio contatti unificato  <br/>&bull;&nbsp;&nbsp;Immagini ad alta risoluzione  <br/>&bull;&nbsp;&nbsp;Integrazione di archiviazione  <br/> **Nota:** Per ulteriori informazioni, vedere [integrazione di Skype for Business Server con Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md).  <br/> |
|Exchange Server 2010  <br/>(Solo per Skype for Business Server 2015) |Le funzionalità seguenti sono disponibili solo tramite i Servizi Web Exchange:  <br/>&bull;&nbsp;&nbsp;Leggere o eliminare gli elementi nella cartella Cronologia conversazioni  <br/>&bull;&nbsp;&nbsp;Lettura o eliminazione di elementi di segreteria telefonica  <br/>&bull;&nbsp;&nbsp;Visualizzare le informazioni sulla disponibilità estese e l'oggetto e la posizione della riunione  <br/>&bull;&nbsp;&nbsp;Sincronizzazione contatti di Exchange  <br/> Le cartelle pubbliche sono facoltative in Exchange Server 2010.  <br/> |
   
## <a name="see-also"></a>Vedere anche
 
[Requisiti del client Windows e supporto software](windows-requirements.md)
  
[Pianificare i client di riunioni (app per le riunioni e le app Web)](meetings-clients.md)

