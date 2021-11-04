---
title: Pianificare le linee telefoniche private con Skype for Business
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 9cc4f9e1-7b7a-4699-bd05-f16669ef2d21
description: Pianificazione di linee telefoniche private (secondarie) in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: 4c4a03d539835a1b776b729c83bdd1bf19e0ff82
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60763474"
---
# <a name="plan-for-private-telephone-lines-with-skype-for-business"></a>Pianificare le linee telefoniche private con Skype for Business
 
Pianificazione di linee telefoniche private (secondarie) in Skype for Business Server VoIP aziendale.
  
Skype for Business Server consente di assegnare agli utenti una seconda linea telefonica privata oltre alla linea telefonica principale. Le linee telefoniche private sono spesso assegnate ai dirigenti e ad altri che desiderano un numero di telefono non in elenco al quale possono essere raggiunte direttamente.
  
Le linee telefoniche private possono essere configurate solo con Skype for Business Server Management Shell. Non è possibile configurare linee telefoniche private con Skype for Business Server pannello di controllo. Le linee telefoniche private devono essere configurate solo nelle distribuzioni di Skype for Business Server e non nelle distribuzioni miste.
  
## <a name="characteristics-of-private-telephone-lines"></a>Caratteristiche delle linee telefoniche private

Sebbene il concetto di una seconda linea telefonica privata sia fondamentalmente semplice, è importante comprendere le caratteristiche delle linee private e i modi in cui sono simili e diverse dalle linee telefoniche principali degli utenti.
  
### <a name="general-characteristics-of-private-telephone-lines"></a>Caratteristiche generali delle linee telefoniche private

- Un utente può avere una sola linea telefonica privata.
    
- Un utente con una linea telefonica privata dispone di una sola cassetta postale vocale e riceve notifiche di chiamata senza risposta in un singolo indirizzo di posta elettronica.
    
- Un utente con una linea telefonica privata non dispone di un secondo indirizzo SIP e una seconda linea telefonica privata non fornisce a un utente una seconda presenza sulla rete (ad esempio, una seconda identità di messaggistica istantanea). 
    
- Le linee telefoniche private sono disponibili solo per le distribuzioni locali. Non sono disponibili con distribuzioni ospitate di Skype for Business Server.
    
### <a name="how-private-telephone-lines-differ-from-primary-telephone-lines"></a>Differenze tra le linee telefoniche private e le linee telefoniche primarie

- I numeri di telefono per le linee telefoniche private non vengono visualizzati nelle directory telefoniche o negli elenchi contatti derivati da Servizi di dominio Active Directory.
    
- Nessuna delle funzionalità seguenti è disponibile con una linea telefonica privata: inoltro di chiamata, chiamata del team, delega, anello del team, prelievo chiamata di gruppo e applicazione Response Group.
    
- Le chiamate a una linea telefonica privata hanno un anello speciale e la notifica di sistema per la chiamata indica all'utente che la chiamata in arrivo si trova sulla sua linea privata.
    
- Le chiamate alla linea telefonica privata squillano sempre. Non seguono le regole "non disturbare".
    
- Le linee telefoniche private sono solo in ingresso e non possono essere utilizzate per effettuare chiamate in uscita. Quando un utente con una linea telefonica privata effettua una chiamata, la chiamata proviene dalla linea telefonica principale dell'utente e non nasconde il nome dell'utente o il numero di telefono principale dell'utente dalla persona chiamata.
    
### <a name="how-private-telephone-lines-are-similar-to-primary-telephone-lines"></a>Come le linee telefoniche private sono simili alle linee telefoniche primarie

- Le chiamate senza risposta a una linea telefonica privata vengono instradate alla stessa posta in arrivo della segreteria telefonica della linea telefonica principale (se la segreteria telefonica è abilitata).
    
- Il parcheggio di chiamata e il prelievo delle chiamate funzionano con linee telefoniche private esattamente nello stesso modo in cui funzionano con la linea telefonica principale dell'utente.
    
- Quando la suoneria simultanea è abilitata sulla linea telefonica principale di un utente, viene abilitata anche sulla linea telefonica privata.
    
- Il numero di telefono di una linea telefonica privata viene registrato nel record dettagli chiamata nello stesso modo del numero di telefono della linea telefonica principale di un utente, ma con un'indicazione che si tratta di un numero di telefono privato.
    
- Dopo che un utente risponde a una chiamata su una linea telefonica privata, la chiamata viene trattata come una chiamata sulla linea telefonica principale dell'utente. Ad esempio, se un utente che riceve una chiamata su una linea telefonica privata inoltra la chiamata o invita altri utenti a una conferenza telefonica, il nome dell'utente viene visualizzato in Skype for Business e il numero di telefono della linea telefonica principale dell'utente viene visualizzato nell'ID chiamante.
    
- Un utente può deviare una chiamata (reindirizzare la chiamata a un'altra destinazione, ad esempio un telefono cellulare o un telefono di casa, prima di rispondere) dalla linea telefonica privata allo stesso modo di una linea telefonica principale. 
    
    > [!NOTE]
    > Quando una chiamata a una linea privata viene instradata a un numero di telefono alternativo, il numero di telefono della linea telefonica privata viene reso disponibile per il numero di telefono alternativo e può essere visualizzato nei registri per tale numero. 
  
    > [!NOTE]
    > Le chiamate da una conferenza alla linea telefonica privata non avranno un'indicazione di linea  *privata*  nella notifica del sistema in arrivo.
  
## <a name="administering-private-telephone-lines"></a>Amministrazione delle linee telefoniche private

Oltre agli aspetti tecnici della creazione e della gestione delle linee telefoniche private, è necessario stabilire procedure amministrative per queste linee. Ciò include la determinazione dei criteri per chi nell'organizzazione è idoneo per una linea privata, la creazione e la gestione di elenchi di persone e linee telefoniche, eventualmente la creazione di una rubrica telefonica privata per i dirigenti, l'organizzazione per la formazione degli utenti e le attività correlate.
  
> [!NOTE]
> La linea telefonica privata viene archiviata in Active Directory come attributo msRTCSIP-PrivateLine nell'oggetto utente. Per impostazione predefinita, qualsiasi membro del gruppo Authenticated Users dispone dell'accesso in lettura a questo attributo. 
  
### <a name="assigning-telephone-numbers"></a>Assegnazione di numeri di telefono

 Gli account per i nuovi utenti che necessitano di linee telefoniche private vengono creati nello stesso modo degli account senza linee telefoniche private, utilizzando il Pannello di controllo di Skype for Business Server o Skype for Business Server Management Shell.
  
Utilizzare il cmdlet **Set-CsUser** in Skype for Business Server Management Shell per assegnare un numero di telefono a una linea telefonica privata per un utente, ad esempio **Set-CsUser -Identity "sip:joe@contoso.com" -PrivateLine "Tel:+14255551212".**
  
I numeri di telefono per le linee telefoniche private possono avere una lunghezza compresa tra 3 e 15 e devono essere preceduti dal prefisso "TEL:". Possono avere qualsiasi codice di area geografica e qualsiasi codice paese/area geografica purché l'organizzazione abbia una composizione diretta verso l'interno per tale codice di area geografica e codice paese/area geografica. 
  
Per informazioni dettagliate sui cmdlet e Skype for Business Server Management Shell, vedere la documentazione Skype for Business Server Management Shell.
  
### <a name="private-telephone-lines-in-mixed-deployments"></a>Linee telefoniche private in distribuzioni miste

Le linee telefoniche private devono essere configurate solo per le distribuzioni di Skype for Business Server o Lync Server 2013. In una distribuzione in cui sono presenti server che eseguono versioni precedenti di Lync Server, quando un utente della versione precedente tenta di chiamare una linea telefonica privata, l'instradamento della chiamata non riesce perché il server non può eseguire una ricerca di numeri inversa su una linea telefonica privata.
  

