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
> Skype for Business Server ora supporta la configurazione di più numeri di emergenza per un client. Se si desidera configurare più numeri di emergenza, è necessario seguire le informazioni in Pianificare più numeri di emergenza [in Skype for Business Server](multiple-emergency-numbers.md) e configurare più numeri di emergenza in Skype for [Business.](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md) 
  
È possibile creare criteri percorso utilizzando il Pannello di controllo di Skype for Business o il cmdlet [New-CsLocationPolicy.](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) Per ulteriori informazioni, vedere [Creare criteri percorso in Skype for Business Server.](../../deploy/deploy-enterprise-voice/create-location-policies.md)
  
Ogni criterio percorso contiene le informazioni seguenti:
  
 **Abilitare enhanced 9-1-1**
  
Quando questo valore è abilitato, il client è abilitato per i servizi di emergenza avanzato (E9-1-1). Quando un client si registra, tenta di acquisire una posizione dal servizio informazioni sulla posizione e include le informazioni sulla posizione come parte di una chiamata di emergenza.
  
 **Posizione**
  
Questa impostazione viene utilizzata solo quando **è abilitato il servizio di 9-1-1** avanzato.
  
È possibile configurare **l'impostazione Percorso** per definire il comportamento del client nel modo seguente:
  
- Se si imposta il **valore su No,** all'utente non verrà richiesto di specificare una posizione.
    
- Se si imposta il valore **su Sì,** all'utente verrà richiesto di specificare una posizione, ma potrà ignorare la richiesta.
    
- Se si imposta il valore su **Disclaimer,** all'utente verrà richiesto di specificare una posizione e verrà visualizzata una dichiarazione di non responsabilità se tenta di ignorare la richiesta. In tutti i casi, l'utente può continuare a usare il client.
    
> [!NOTE]
> Il testo della dichiarazione di non responsabilità non verrà visualizzato se un utente ha immesso manualmente una posizione prima di essere abilitato per il servizio E9-1-1. Gli aggiornamenti al testo della dichiarazione di non responsabilità non verranno visualizzati dagli utenti che hanno già visualizzato la dichiarazione di non responsabilità. 
  
 **Dichiarazione di non responsabilità del servizio di emergenza avanzato**
  
Questa impostazione consente di specificare la dichiarazione di non responsabilità che gli utenti visualizzano se ignorano la richiesta di una posizione. In Skype for Business Server, è possibile utilizzare i criteri percorso per impostare dichiarazioni di non responsabilità diverse per impostazioni locali o set di utenti diversi.
  
 **Stringa di composizione per gli interventi di emergenza (numero di composizione E9-1-1)**
  
Questa stringa di composizione (meno il "+" iniziale, ma includendo qualsiasi normalizzazione eseguita dal dial plan dell'utente) significa che una chiamata è una chiamata di emergenza. La **stringa di composizione per gli** interventi di emergenza fa sì che il client includa informazioni sulla posizione e sulla richiamata con la chiamata.
  
> [!NOTE]
> Se l'organizzazione non utilizza un prefisso di accesso alla linea esterna, non è necessario creare una regola di normalizzazione dial plan corrispondente che aggiunge un "+" alla stringa 911 prima di inviare la chiamata al routing in uscita su un server che esegue Skype for Business Server; il "+" verrà anteposto automaticamente dal client Skype for Business come risultato dei criteri percorso. Tuttavia, se il sito utilizza un prefisso di accesso esterno, è necessario aggiungere una regola di normalizzazione al criterio dial plan applicabile che rimuove il prefisso di accesso esterno e aggiunge il "+". Ad esempio, se la posizione utilizza un prefisso di accesso esterno 9 e un utente compone il numero 9 911 per effettuare una chiamata di emergenza, il client utilizzerà il relativo criterio dial plan per normalizzare il numero su +911 prima che il numero composto venga valutato dalle route nel profilo di posizione del chiamante. 
  
 **Maschere stringa di composizione di emergenza (maschera di composizione E9-1-1)**
  
Elenco di stringhe di composizione separate da punto e virgola che viene convertito nella stringa di **composizione di emergenza specificata.** Ad esempio, è possibile aggiungere 112, che è il numero del servizio di emergenza per la maggior parte dell'Europa. Un utente di Skype for Business in visita dall'Europa potrebbe non sapere che il 911 è il numero di emergenza degli Stati Uniti, ma può comporre il 112 e ottenere lo stesso risultato. Come per la stringa di composizione per gli interventi di emergenza, non includere un "+" prima di ogni numero e, se si utilizzano codici di accesso alla linea esterna, assicurarsi che nel criterio dial plan dell'utente siano presenti regole di normalizzazione per rimuovere la cifra del codice di accesso.
  
 **Utilizzo PSTN**
  
Nome dell'utilizzo PSTN contenente i percorsi di routing che determinano a quale trunk SIP, gateway PSTN o gateway ELIN verranno effettuate le chiamate di emergenza.
  
> [!NOTE]
> È possibile assegnare un solo utilizzo a un criterio percorso. Questo utilizzo PSTN sostituisce gli utilizzi PSTN assegnati ai criteri vocali dell'utente, ma si applica solo alle chiamate effettuate alla stringa di composizione di emergenza o a una delle maschere della stringa di composizione di emergenza. 
  
 **URI notifica**
  
Specifica uno o più URI SIP del personale di sicurezza che riceve una notifica di messaggistica istantanea quando viene inviata una chiamata di emergenza. Sono supportati i gruppi di distribuzione.
  
 **URI conferenza**
  
Specifica un numero DID (Direct Inward Dialing) (in genere un numero del desk di sicurezza) a cui effettuare una conferenza quando viene messa una chiamata di emergenza. 
  
 **Modalità conferenza**
  
Specifica se l'URI della conferenza verrà inserito nella chiamata di emergenza utilizzando una comunicazione unidirezionale o bidirezionale. 
  
 **Intervallo di aggiornamento della posizione**
  
Specifica l'intervallo di tempo, in ore, tra le richieste client per un aggiornamento della posizione dal servizio Informazioni percorso. Il valore può essere impostato su qualsiasi valore compreso tra 1 e 12. Il valore predefinito è 4.
  

