---
title: Pianificare i criteri percorso per Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: da3cca7f-f6e5-4b6f-90a1-2008e3dd1ebd
description: Leggere questo argomento per informazioni su come pianificare i criteri percorso per una distribuzione di servizi di emergenza avanzata (E9-1-1) in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: 1e89c2f0ea9d5115b29e9bc6d77b3863bb11888c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825536"
---
# <a name="plan-location-policies-for-skype-for-business-server"></a>Pianificare i criteri percorso per Skype for Business Server
 
Leggere questo argomento per informazioni su come pianificare i criteri percorso per una distribuzione di servizi di emergenza avanzata (E9-1-1) in Skype for Business Server VoIP aziendale. 
  
> [!NOTE]
> Skype for Business Server ora supporta la configurazione di più numeri di emergenza per un client. Se si desidera configurare più numeri di emergenza, è necessario seguire le informazioni in [pianificare numeri di emergenza multipli in Skype for Business Server](multiple-emergency-numbers.md) e [configurare più numeri di emergenza in Skype for business](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md). 
  
È possibile creare criteri percorso utilizzando il pannello di controllo di Skype for business o utilizzando il cmdlet [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) . Per ulteriori informazioni, vedere [create location Policies in Skype for Business Server](../../deploy/deploy-enterprise-voice/create-location-policies.md).
  
Ogni criterio percorso contiene le informazioni seguenti:
  
 **Abilitare Enhanced 9-1-1**
  
Quando questo valore è abilitato, il client è abilitato per i servizi di emergenza avanzati (E9-1-1). Quando un client si registra, tenta di acquisire una posizione dal servizio informazioni percorso e includerà le informazioni sul percorso come parte di una chiamata di emergenza.
  
 **Posizione**
  
Questa impostazione viene utilizzata solo quando è abilitata l'opzione **attiva Enhanced 9-1-1** .
  
È possibile configurare l'impostazione **percorso** per definire il comportamento del client come indicato di seguito:
  
- L'impostazione del valore su **No** significa che all'utente non verrà richiesto un percorso.
    
- Se si imposta il valore su **Sì** , l'utente riceverà la richiesta di una posizione, ma può ignorare il prompt.
    
- Se si imposta il valore come dichiarazione di non **responsabilità** , all'utente verrà richiesto un percorso e verrà visualizzata una dichiarazione di non responsabilità se si tenta di eliminare il messaggio. In tutti i casi, l'utente può continuare a utilizzare il client.
    
> [!NOTE]
> Il testo della dichiarazione di non responsabilità non verrà visualizzato se un utente ha immesso manualmente una posizione prima di essere abilitato per il servizio E9-1-1. Gli aggiornamenti del testo della dichiarazione di non responsabilità non verranno visualizzati dagli utenti che hanno già visualizzato la dichiarazione di non responsabilità. 
  
 **Dichiarazione di non responsabilità avanzata del servizio di emergenza**
  
Questa impostazione consente di specificare la dichiarazione di non responsabilità che gli utenti vedranno se ignorano la richiesta di un percorso. In Skype for Business Server, è possibile utilizzare i criteri percorso per impostare diverse dichiarazioni di non responsabilità per le diverse impostazioni locali o gruppi di utenti diversi.
  
 **Stringa di chiamata di emergenza (numero di chiamata E9-1-1)**
  
Questa stringa di composizione (meno la principale "+", ma inclusa la normalizzazione fatta dal dial plan dell'utente) significa che una chiamata è una chiamata di emergenza. La **stringa di composizione di emergenza** induce il client a includere le informazioni sul percorso e sulla richiamata tramite la chiamata.
  
> [!NOTE]
> Se l'organizzazione non utilizza un prefisso di accesso alla linea esterna, non è necessario creare una regola di normalizzazione del dial plan corrispondente che aggiunga una "+" alla stringa 911 prima di inviare la chiamata al routing in uscita su un server su cui è in esecuzione Skype for Business Server. il "+" verrà anteposto automaticamente dal client Skype for business a causa del criterio percorso. Tuttavia, se il sito utilizza un prefisso di accesso esterno, è necessario aggiungere una regola di normalizzazione al criterio del dial plan applicabile che rimuove il prefisso di accesso esterno e aggiunge "+". Ad esempio, se la posizione utilizza un prefisso di accesso esterno pari a 9 e un utente compone 9 911 per effettuare una chiamata di emergenza, il client utilizzerà i criteri di dial plan per normalizzare questo valore su + 911 prima che il numero composto venga valutato dalle route nel profilo località del chiamante. 
  
 **Maschere della stringa di chiamata di emergenza (maschera di chiamata E9-1-1)**
  
Elenco separato da punto e virgola di stringhe di composizione che vengono convertite nella **stringa di chiamata di emergenza** specificata. Ad esempio, si consiglia di aggiungere 112, che è il numero di servizio di emergenza per la maggior parte dell'Europa. Un utente che visita Skype for business dall'Europa potrebbe non sapere che 911 è il numero di emergenza degli Stati Uniti, ma può comporre 112 e ottenere lo stesso risultato. Analogamente alla stringa di chiamata di emergenza, non includere un "+" prima di ogni numero e se si utilizzano codici di accesso alla linea esterna, accertarsi che siano presenti regole di normalizzazione nel criterio di dial plan dell'utente per eliminare la cifra del codice di accesso.
  
 **Utilizzo PSTN**
  
Nome dell'utilizzo PSTN che contiene i percorsi di routing che determinano il trunk SIP, il gateway PSTN o le chiamate di emergenza del gateway ELIN.
  
> [!NOTE]
> È possibile assegnare un solo utilizzo a un criterio percorso. Questo utilizzo PSTN sostituisce gli utilizzi PSTN assegnati ai criteri vocali dell'utente, ma si applica solo alle chiamate effettuate alla stringa di chiamata di emergenza o a una delle maschere di chiamata di stringa di emergenza. 
  
 **URI di notifica**
  
Specifica uno o più URI SIP del personale di sicurezza che ricevono una notifica di messaggistica istantanea quando viene effettuata una chiamata di emergenza. Sono supportati i gruppi di distribuzione.
  
 **URI conferenza**
  
Specifica un numero DID (Direct Inward Dialing) (in genere, un numero del desk di sicurezza) che dovrebbe essere utilizzato per la conferenza quando viene effettuata una chiamata di emergenza. 
  
 **Modalità conferenza**
  
Specifica se l'URI conferenza verrà configurata nella chiamata di emergenza utilizzando una comunicazione unidirezionale o bidirezionale. 
  
 **Intervallo di aggiornamento delle posizioni**
  
Specifica la quantità di tempo (in ore) tra le richieste dei client per un aggiornamento del percorso dal servizio informazioni percorso. Il valore può essere impostato su qualsiasi valore compreso tra 1 e 12. Il valore predefinito è 4.
  

