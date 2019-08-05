---
title: Pianificare i criteri di posizione per Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: da3cca7f-f6e5-4b6f-90a1-2008e3dd1ebd
description: Leggere questo argomento per informazioni su come pianificare i criteri di posizione per una distribuzione di servizi di emergenza avanzata (E9-1-1) in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: 8f21a5a0f54fbeaca4c46ed51bf4dafe4c2a3dcb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187649"
---
# <a name="plan-location-policies-for-skype-for-business-server"></a>Pianificare i criteri di posizione per Skype for Business Server
 
Leggere questo argomento per informazioni su come pianificare i criteri di posizione per una distribuzione di servizi di emergenza avanzata (E9-1-1) in Skype for Business Server VoIP aziendale. 
  
> [!NOTE]
> Skype for Business Server ora supporta la configurazione di più numeri di emergenza per un client. Se si vogliono configurare più numeri di emergenza, è necessario seguire le informazioni in [piano per i numeri di emergenza multipli in Skype for Business Server](multiple-emergency-numbers.md) e [configurare più numeri di emergenza in Skype for business](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md). 
  
È possibile creare criteri di posizione usando il pannello di controllo di Skype for business o usando il cmdlet [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) . Per altre informazioni, vedere [creare criteri di posizione in Skype for Business Server](../../deploy/deploy-enterprise-voice/create-location-policies.md).
  
Ogni criterio di posizione contiene le informazioni seguenti:
  
 **Abilitare 9-1-1 avanzato**
  
Quando questo valore è abilitato, il client è abilitato per i servizi di emergenza avanzati (E9-1-1). Quando un client esegue la registrazione, tenta di acquisire una posizione dal servizio informazioni sulla posizione e includerà le informazioni sulla posizione come parte di una chiamata di emergenza.
  
 **Posizione**
  
Questa impostazione viene usata solo quando è abilitato **Enable Enhanced 9-1-1** .
  
Puoi configurare l'impostazione della **posizione** per definire il comportamento del client nel modo seguente:
  
- Impostando il valore su **No** , l'utente non verrà richiesto per una posizione.
    
- Impostando il valore su **Sì** , l'utente verrà richiesto per una posizione, ma può chiudere la richiesta.
    
- Se si imposta il valore su **Disclaimer** , l'utente verrà richiesto di ricevere una posizione e verrà visualizzata anche una dichiarazione di non responsabilità se tenta di chiudere la richiesta. In tutti i casi, l'utente può continuare a usare il client.
    
> [!NOTE]
> Il testo della dichiarazione di non responsabilità non verrà visualizzato se un utente ha immesso manualmente una posizione prima di essere abilitato per il E9-1-1. Gli aggiornamenti al testo della dichiarazione di non responsabilità non verranno visualizzati dagli utenti che hanno già visualizzato la dichiarazione di non responsabilità. 
  
 **Dichiarazione di non responsabilità avanzata del servizio di emergenza**
  
Questa impostazione specifica la dichiarazione di non responsabilità che gli utenti vedono se eliminano la richiesta di una posizione. In Skype for Business Server è possibile usare i criteri di posizione per impostare dichiarazioni di non credito diverse per le diverse impostazioni locali o per diversi gruppi di utenti.
  
 **Stringa di chiamata di emergenza (numero di telefono E9-1-1)**
  
Questa stringa di chiamata (meno l'iniziale "+", ma anche qualsiasi normalizzazione eseguita dal dial plan dell'utente) indica che una chiamata è una chiamata di emergenza. La **stringa** di chiamata di emergenza fa sì che il client includa le informazioni sulla posizione e sulla richiamata con la chiamata.
  
> [!NOTE]
> Se l'organizzazione non usa un prefisso di accesso alla linea esterna, non è necessario creare una regola di normalizzazione del dial plan corrispondente che aggiunga un "+" alla stringa 911 prima di inviare la chiamata al routing in uscita in un server che esegue Skype for Business Server; il "+" verrà anteposto automaticamente dal client Skype for business come risultato dei criteri di posizione. Tuttavia, se il sito usa un prefisso di accesso esterno, è necessario aggiungere una regola di normalizzazione ai criteri di dial plan applicabili che allineano il prefisso di accesso esterno e aggiunge "+". Ad esempio, se la tua posizione usa un prefisso di accesso esterno di 9 e un utente compone 9 911 per effettuare una chiamata di emergenza, il client userà i criteri per il dial plan per normalizzare questa operazione su + 911 prima che il numero composto venga valutato dalle route nel profilo della posizione del chiamante. 
  
 **Maschere di stringhe di chiamate di emergenza (E9-1-1 Dial mask)**
  
Elenco separato da punti e virgola delle stringhe di chiamata tradotte nella **stringa di chiamata di emergenza**specificata. Ad esempio, potresti voler aggiungere 112, che è il numero di servizio di emergenza per la maggior parte dell'Europa. Un utente di Skype for business che visita l'Europa potrebbe non sapere che 911 è il numero di emergenza degli Stati Uniti, ma può chiamare 112 e ottenere lo stesso risultato. Come per la stringa di chiamata di emergenza, non includere un "+" prima di ogni numero e se si usano i codici di accesso per le linee esterne, verificare che esistano regole di normalizzazione nei criteri di dial plan dell'utente per eliminare la cifra del codice di accesso.
  
 **Utilizzo PSTN**
  
Nome dell'utilizzo PSTN che contiene i percorsi di routing che determinano il trunk SIP, il gateway PSTN o le chiamate di emergenza del gateway ELIN.
  
> [!NOTE]
> Un solo utilizzo può essere assegnato a un criterio di posizione. Questo uso PSTN esegue l'override degli usi PSTN assegnati al criterio vocale dell'utente, ma si applica solo alle chiamate poste alla stringa di chiamata di emergenza o a una delle maschere di stringhe di chiamata di emergenza. 
  
 **URI di notifica**
  
Specifica uno o più URI SIP del personale di sicurezza che riceve una notifica di messaggistica istantanea quando viene inserita una chiamata di emergenza. I gruppi di distribuzione sono supportati.
  
 **URI conferenza**
  
Specifica un numero DID (Direct Interior Dialing) (in genere un numero di banco di sicurezza) che deve essere convogliato in conferenza quando viene inserita una chiamata di emergenza. 
  
 **Modalità conferenza**
  
Specifica se l'URI della conferenza verrà conferito alla chiamata di emergenza tramite una comunicazione unidirezionale o bidirezionale. 
  
 **Intervallo di aggiornamento della posizione**
  
Specifica la quantità di tempo (in ore) tra le richieste client per un aggiornamento della posizione dal servizio informazioni sulla posizione. Il valore può essere impostato su qualsiasi valore compreso tra 1 e 12. Il valore predefinito è 4.
  

