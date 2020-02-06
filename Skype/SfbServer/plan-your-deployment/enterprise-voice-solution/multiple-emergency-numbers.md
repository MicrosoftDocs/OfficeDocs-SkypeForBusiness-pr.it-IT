---
title: Pianificare più numeri di emergenza in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.assetid: 5ed45a22-ddf0-419f-84da-895a73df855f
description: Leggere questo argomento per informazioni su come pianificare più numeri di emergenza in Skype for Business Server.
ms.openlocfilehash: 6f10b5c22a26a42f33f2a3b453dd2e244c9f32ee
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815964"
---
# <a name="plan-for-multiple-emergency-numbers-in-skype-for-business-server"></a>Pianificare più numeri di emergenza in Skype for Business Server
 
Leggere questo argomento per informazioni su come pianificare più numeri di emergenza in Skype for Business Server.
  
Skype for Business Server ora supporta la configurazione di più numeri di emergenza per un client. Più numeri di emergenza è una nuova funzionalità introdotta nell'aggiornamento cumulativo di giugno 2016. Mentre gli Stati Uniti hanno un singolo numero di emergenza, 911, molti paesi supportano più numeri di emergenza. Il Regno Unito, ad esempio, supporta sia 999, il numero di emergenza specifico per il Regno Unito, che 112, il numero di emergenza per l'Unione europea. 
  
Questa funzionalità è utile anche per i provider di servizi sanitari all'interno degli Stati Uniti che desiderano avere il supporto per il roaming per più numeri di emergenza blu per il codice.
  
## <a name="multiple-emergency-numbers-and-location-policies"></a>Più numeri di emergenza e criteri di posizione

Per configurare le chiamate di emergenza, è possibile creare criteri di posizione che definiscono la modalità di implementazione delle chiamate di emergenza. Si usano i criteri di posizione per definire il numero che costituisce una chiamata di emergenza, ad esempio 911 negli Stati Uniti; 999 e 112 nel Regno Unito. I criteri di posizione determinano se un utente è abilitato per le chiamate di emergenza e, in caso affermativo, qual è il comportamento di una chiamata di emergenza. Puoi anche definire se la sicurezza aziendale deve essere notificata automaticamente e come deve essere instradata la chiamata.
  
Per altre informazioni sulla definizione e la modifica dei criteri di posizione, vedere [pianificare i criteri di posizione per Skype for Business Server](location-policies.md) e [creare criteri di posizione in Skype for Business Server](../../deploy/deploy-enterprise-voice/create-location-policies.md). Questi argomenti descrivono i concetti relativi ai criteri di posizione; Devi tuttavia seguire le istruzioni in [configurare più numeri di emergenza in Skype for business](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md) per configurare più numeri di emergenza.
  
Quando si pianificano più numeri di emergenza, tieni presente quanto segue:
  
- Con l'aggiornamento cumulativo di giugno 2016 è possibile definire fino a 5 numeri di emergenza per un criterio di posizione specifico. Con l'aggiornamento cumulativo di novembre 2016, questo numero aumenta fino a 100.
    
    > [!NOTE]
    > Se l'aggiornamento cumulativo di novembre 2016 non è stato ancora aggiornato, vedere [aggiornamenti di Skype for Business Server 2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015). 
  
- Per ogni numero di emergenza, è possibile specificare zero o più maschere di chiamata di emergenza, che sono univoche per un criterio di posizione specifico.
    
    Una maschera di chiamata è un numero che si vuole tradurre nel valore del valore del numero di telefono di emergenza quando viene composto. Supponiamo ad esempio di immettere un valore di 212 in questo campo e il campo numero di chiamata di emergenza ha un valore di 911. Quando un utente compone 212, il numero verrà convertito in 911. In questo modo, i numeri di emergenza alternativi devono essere composti e i servizi di emergenza REACH (ad esempio, se qualcuno di un paese o di un'area geografica con un numero di emergenza diverso cerca di chiamare il numero del paese o dell'area geografica invece del numero paese o area geografica in cui si trovano attualmente. Puoi definire più maschere di chiamate di emergenza separando i valori con punti e virgola. Ad esempio, 212; 414. Il limite di stringa per una maschera di chiamata è di 100 caratteri. Ogni carattere deve essere una cifra da 0 a 9.
    
- Ogni criterio di posizione include un singolo utilizzo PSTN (Public Switched Telephone Network) usato per determinare quale route vocale viene usata per instradare chiamate di emergenza da client che usano questo criterio. L'utilizzo può avere un percorso univoco per ogni numero di emergenza.
    
- Se un criterio di posizione include sia i parametri EmergencyNumbers che DialString definiti e il client supporta più numeri di emergenza, il numero di emergenza avrà la precedenza. Se il client non supporta più numeri di emergenza, viene usata la stringa di chiamata di emergenza.
    
- Per informazioni sui client Skype for business e Lync che supportano la ricezione di più numeri di emergenza, Dial mask e usi pubblici PSTN (Public Switched Telephone Network), vedere [supporto client](multiple-emergency-numbers.md#BKMK_Clients).
    
> [!NOTE]
> Non è possibile configurare più numeri di emergenza usando il pannello di controllo di Skype for business. Devi usare PowerShell per configurare più numeri di emergenza. 
  
Prima di configurare più numeri di emergenza, tieni presente quanto segue:
  
- Per configurare più numeri di emergenza, è necessario utilizzare il cmdlet New-CsEmergencyNumber ed è necessario definire i criteri di posizione che supportano più di un numero di emergenza specificando il parametro EmergencyNumbers con i cmdlet [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) e [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) .
    
- Se i numeri esistenti sono definiti usando il cmdlet Set-CsLocationPolicy o New-CsLocationPolicy con i parametri EmergencyDialString e EmergencyDialMask, i valori specificati con il parametro EmergencyNumbers avranno la precedenza sui vecchi valori. I valori dei parametri EmergencyDialString e EmergencyDialMask verranno ignorati.
    
- Se i numeri esistenti sono definiti usando il cmdlet Set-CsLocationPolicy o New-CsLocationPolicy con i parametri EmergencyDialString e EmergencyDialMask *e non vengono configurati nuovi numeri di emergenza* , i numeri esistenti continueranno a essere usati.
    
- Per il funzionamento della funzionalità numeri di emergenza multipli, le versioni client in uso devono essere in grado di supportare la nuova funzionalità. I client meno recenti continueranno a usare i vecchi valori specificati dai cmdlet Set-CsLocationPolicy o New-CsLocationPolicy con i parametri EmergencyDialString e EmergencyDialMask. 
    
- Se gli utenti comporrà un numero corrispondente alla stringa di chiamata, non è necessaria alcuna maschera di chiamata. Ad esempio, se il numero che un utente compone è 911, la stringa di chiamata è 911 e non è richiesta alcuna maschera. 
    
Per altre informazioni sulla configurazione di più numeri di emergenza, vedere [configurare più numeri di emergenza in Skype for business](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md).
  
La tabella seguente mostra i criteri di posizione di esempio (ai fini dell'esempio non vengono visualizzati tutti gli attributi):
  

|**Nome dei criteri di posizione**|**E911 abilitato**|**Stringa di chiamata di emergenza**|**Maschera di chiamata**|**Numeri di emergenza**|**Utilizzo PSTN**|**Posizione richiesta**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Stati Uniti  <br/> |Sì  <br/> |911  <br/> | 112; 999 <br/> ||USEmergency  <br/> |Sì  <br/> |
|Stati Uniti-ospedale  <br/> |Sì  <br/> |911  <br/> |450  <br/> |911  <br/> 450  <br/> |SeattleEmergency  <br/> |Sì  <br/> |
|Londra  <br/> |Sì  <br/> |999  <br/> |144  <br/> |999-144  <br/> 112-911; 117; 118  <br/> |GBEmergency  <br/> |No  <br/> |
|India  <br/> |Sì  <br/> |||100-911  <br/> 101  <br/> 102  <br/> |IndiaEmergency  <br/> |No  <br/> |
   
 **Stati Uniti** -non esiste alcun requisito per i numeri di emergenza multipli. Negli Stati Uniti si usano le vecchie configurazioni della stringa di chiamata in emergenza e della maschera di chiamata.
  
 **Stati Uniti-ospedale** -c'è un requisito per non mascherare "450". Per i client che non supportano ancora numeri di emergenza multipli, è possibile usare le vecchie configurazioni della stringa di chiamata e della maschera di emergenza. Per i client che supportano più numeri di emergenza, è possibile definire un numero di emergenza sia per "911" che per "450" invece di mascherare 450.
  
 **Milano** -per i client che non supportano ancora più numeri di emergenza, è possibile usare le vecchie configurazioni della stringa di chiamata e della maschera di emergenza. Per i client che supportano più numeri di emergenza, è possibile definire un numero di emergenza sia per "999" che per "112" con maschere per ogni.
  
 **India** -tutti i client distribuiti supportano più numeri di emergenza. In India è sufficiente configurare più numeri di emergenza.
  
## <a name="client-support"></a>Supporto client
<a name="BKMK_Clients"> </a>

La tabella seguente mostra il supporto client per più numeri di emergenza. Microsoft continuerà a testare e rilasciare il supporto per altri client. Controlla spesso di nuovo.

|**Windows**|**Versione**|
|:-----|:-----|
|**A portata di clic** <br/> |CC (Current Channel) rilasciata il 10 maggio 2016-versione 1604 (Build 6868,2062)  <br/> |
||FRDC (First Release Current Channel) rilasciata il 14 giugno 2016-versione 1605 (Build 6965,2058)  <br/> |
||DC (Deferred Channel) rilasciata il 11 ottobre 2016-versione 1605 (Build 6965,2092)  <br/> |
|**MSI** <br/> |Aggiornamento del 7 giugno-[https://support.microsoft.com/en-us/kb/3115087](https://support.microsoft.com/en-us/kb/3115087) <br/> |
|**Mac e iOS** <br/> |**Versione** <br/> |
||Client di Skype for business per Mac versione 16,9  <br/> Client iOS per Skype for Business versione 6,16  <br/> |
|**Android** <br/> |**Versione** <br/> |
||Client Android per Skype for Business versione 6,17  <br/> |
|**Lync Phone Edition** <br/> |**Versione** <br/> |
|| Aastra 6721ip e Aastra 6725ip telefoni-aggiornamento cumulativo 2016 settembre (Build 7577,4512)-[https://support.microsoft.com/en-us/kb/3194831](https://support.microsoft.com/en-us/kb/3194831) <br/> |
|| Telefoni HP 4110 e HP 4120-aggiornamento cumulativo di settembre 2016 (Build 7577,4512)-[https://support.microsoft.com/en-us/kb/3194832](https://support.microsoft.com/en-us/kb/3194832) <br/> |
||Polycom CX500, Polycom CX600 e Polycom CX3000 telefoni-aggiornamento cumulativo settembre 2016 (Build 7577,4512)-[https://support.microsoft.com/en-us/kb/3194833](https://support.microsoft.com/en-us/kb/3194833) <br/> |
   

