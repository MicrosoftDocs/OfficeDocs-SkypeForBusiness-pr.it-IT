---
title: Pianificare numeri di emergenza multipli in Skype for Business Server
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
ms.assetid: 5ed45a22-ddf0-419f-84da-895a73df855f
description: Leggere questo argomento per informazioni su come pianificare più numeri di emergenza in Skype for Business Server.
ms.openlocfilehash: eb5fbc55bc7f2e783fbfa98c7bc7fb6db67ff748
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813866"
---
# <a name="plan-for-multiple-emergency-numbers-in-skype-for-business-server"></a>Pianificare numeri di emergenza multipli in Skype for Business Server
 
Leggere questo argomento per informazioni su come pianificare più numeri di emergenza in Skype for Business Server.
  
Skype for Business Server ora supporta la configurazione di più numeri di emergenza per un client. Numeri di emergenza multipli è una nuova funzionalità introdotta nell'aggiornamento cumulativo di giugno 2016. Mentre gli Stati Uniti hanno un singolo numero di emergenza, 911, molti paesi supportano numeri di emergenza multipli. Il Regno Unito, ad esempio, supporta entrambi 999, il numero di emergenza specifico per il Regno Unito e 112, il numero di emergenza per l'Unione europea. 
  
Questa funzionalità è utile anche per i provider di servizi di assistenza sanitaria all'interno degli Stati Uniti che desiderano disporre del supporto per il roaming per numeri di emergenza blu per più codici.
  
## <a name="multiple-emergency-numbers-and-location-policies"></a>Numeri di emergenza multipli e criteri percorso

Le chiamate di emergenza vengono configurate creando criteri percorso che definiscono la modalità di implementazione delle chiamate di emergenza. È possibile utilizzare il criterio percorso per definire il numero costituito da una chiamata di emergenza, ad esempio 911 negli Stati Uniti. 999 e 112 nel Regno Unito. I criteri percorso determinano se un utente è abilitato per le chiamate di emergenza e, in caso affermativo, qual è il comportamento di una chiamata di emergenza. È inoltre possibile definire se la sicurezza aziendale deve essere notificata automaticamente e come deve essere instradata la chiamata.
  
Per ulteriori informazioni sulla definizione e la modifica di un criterio percorso, vedere [Plan location Policies for Skype for Business Server](location-policies.md) e [create location Policies in Skype for Business Server](../../deploy/deploy-enterprise-voice/create-location-policies.md). In questi argomenti vengono descritti i concetti relativi ai criteri percorso. Tuttavia, è necessario seguire le istruzioni riportate in [configurare più numeri di emergenza in Skype for business](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md) per configurare più numeri di emergenza.
  
Quando si pianificano più numeri di emergenza, tenere presente quanto segue:
  
- Con l'aggiornamento cumulativo di giugno 2016, è possibile definire fino a 5 numeri di emergenza per un determinato criterio percorso. Con l'aggiornamento cumulativo di novembre 2016, questo numero aumenta fino a 100.
    
    > [!NOTE]
    > Se non è stato ancora aggiornato all'aggiornamento cumulativo del 2016 novembre, vedere Updates [to Skype for Business Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015). 
  
- Per ogni numero di emergenza, è possibile specificare zero o più maschere di chiamata di emergenza, che sono univoci per un determinato criterio percorso.
    
    Una maschera di chiamata è un numero che si desidera tradurre nel valore del valore del numero di composizione di emergenza quando viene composto. Si supponga, ad esempio, di immettere il valore 212 in questo campo e il campo numero di composizione di emergenza ha un valore pari a 911. Quando un utente compone 212, il numero verrà convertito in 911. In questo modo è possibile comporre numeri di emergenza alternativi e continuare a chiamare i servizi di emergenza REACH (ad esempio, se un utente di un paese o un'area geografica con un numero di emergenza diverso cerca di comporre il numero del paese o dell'area geografica anziché il numero del paese o dell'area geografica in cui si trovano attualmente). È possibile definire più maschere di composizione del numero di emergenza separando i valori con un punto e virgola. Ad esempio, 212; 414. Il limite di stringa per una maschera di chiamata è 100 caratteri. Ogni carattere deve essere costituito da una cifra compresa tra 0 e 9.
    
- Ogni criterio percorso dispone di un singolo utilizzo PSTN (Public Switched Telephone Network) che viene utilizzato per determinare la route vocale utilizzata per instradare le chiamate di emergenza provenienti dai client che utilizzano questo criterio. L'utilizzo può avere una route univoca per numero di emergenza.
    
- Se i criteri di percorso dispongono entrambi dei parametri EmergencyNumbers e DialString e il client supporta più numeri di emergenza, il numero di emergenza avrà la precedenza. Se il client non supporta più numeri di emergenza, viene utilizzata la stringa di chiamata di emergenza.
    
- Per informazioni su quali client Skype for business e Lync supportano la ricezione di più numeri di emergenza, maschere di chiamata e utilizzo della rete PSTN (Public Switched Telephone Network), vedere [client support](multiple-emergency-numbers.md#BKMK_Clients).
    
> [!NOTE]
> Non è possibile configurare più numeri di emergenza utilizzando il pannello di controllo di Skype for business. È necessario utilizzare PowerShell per configurare più numeri di emergenza. 
  
Prima di configurare più numeri di emergenza, tenere presente quanto segue:
  
- Per configurare più numeri di emergenza, è necessario utilizzare il cmdlet New-CsEmergencyNumber ed è necessario definire i criteri percorso che supportano più di un numero di emergenza specificando il parametro EmergencyNumbers con i cmdlet [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) e [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) .
    
- Se sono stati definiti numeri esistenti utilizzando il cmdlet Set-CsLocationPolicy o New-CsLocationPolicy con i parametri EmergencyDialString e EmergencyDialMask, i valori specificati con il parametro EmergencyNumbers avranno la precedenza sui valori precedenti. In altri modo, i valori per i parametri EmergencyDialString e EmergencyDialMask verranno ignorati.
    
- Se sono presenti numeri già definiti utilizzando il cmdlet Set-CsLocationPolicy o New-CsLocationPolicy con i parametri EmergencyDialString e EmergencyDialMask  *e non vengono configurati nuovi numeri di emergenza*  , i numeri esistenti continueranno a essere utilizzati.
    
- Affinché la funzionalità numeri di emergenza multipli funzioni, le versioni client in esecuzione devono essere in grado di supportare la nuova funzionalità. I client meno recenti continueranno a utilizzare i valori obsoleti specificati dai cmdlet Set-CsLocationPolicy o New-CsLocationPolicy con i parametri EmergencyDialString e EmergencyDialMask. 
    
- Se gli utenti compongono un numero corrispondente alla stringa di composizione, non è necessaria alcuna maschera di chiamata. Ad esempio, se il numero che un utente compone è 911, la stringa di composizione è 911 e non è necessaria alcuna maschera. 
    
Per ulteriori informazioni sulla configurazione di più numeri di emergenza, vedere [configurare più numeri di emergenza in Skype for business](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md).
  
Nella tabella seguente vengono illustrati i criteri percorso di esempio (ai fini dell'esempio, non vengono visualizzati tutti gli attributi):
  

|**Nome del criterio percorso**|**E911 abilitato**|**Stringa di chiamata di emergenza**|**Maschera di chiamata**|**Numeri di emergenza**|**Utilizzo PSTN**|**Posizione obbligatoria**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Stati Uniti  <br/> |Sì  <br/> |911  <br/> | 112; 999 <br/> ||USEmergency  <br/> |Sì  <br/> |
|US-Hospital  <br/> |Sì  <br/> |911  <br/> |450  <br/> |911  <br/> 450  <br/> |SeattleEmergency  <br/> |Sì  <br/> |
|Londra  <br/> |Sì  <br/> |999  <br/> |144  <br/> |999-144  <br/> 112-911; 117; 118  <br/> |GBEmergency  <br/> |No  <br/> |
|India  <br/> |Sì  <br/> |||100-911  <br/> 101  <br/> 102  <br/> |IndiaEmergency  <br/> |No  <br/> |
   
 **Stati Uniti** : non sono previsti requisiti per numeri di emergenza multipli. Negli Stati Uniti, è possibile utilizzare le configurazioni della stringa Dial e della maschera di emergenza precedenti.
  
 **US-Hospital** : è necessario non mascherare "450". Per i client che non supportano ancora numeri di emergenza multipli, è possibile utilizzare le configurazioni della stringa Dial e della maschera di emergenza precedenti. Per i client che supportano numeri di emergenza multipli, è possibile definire un numero di emergenza sia per "911" che per "450" invece di mascherare 450.
  
 **Londra** : per i client che non supportano ancora numeri di emergenza multipli, è possibile utilizzare le configurazioni della stringa di chiamata e della maschera di emergenza precedenti. Per i client che supportano più numeri di emergenza, è possibile definire un numero di emergenza sia per "999" che per "112" con maschere per ognuna.
  
 **India** : tutti i client distribuiti supportano più numeri di emergenza. In India, è sufficiente configurare più numeri di emergenza.
  
## <a name="client-support"></a>Supporto client
<a name="BKMK_Clients"> </a>

Nella tabella seguente viene illustrato il supporto client per più numeri di emergenza. Microsoft continuerà a testare e rilasciare il supporto per i client aggiuntivi. Controllare nuovamente in seguito.

|**Windows**|**Versione**|
|:-----|:-----|
|**A portata di clic** <br/> |CC (Current Channel) rilasciata il 10 maggio 2016-versione 1604 (Build 6868,2062)  <br/> |
||FRDC (First Release Current Channel) rilasciata il 14 giugno 2016-Version 1605 (Build 6965,2058)  <br/> |
||DC (Deferred Channel) rilasciata l'11 ottobre 2016-Version 1605 (Build 6965,2092)  <br/> |
|**MSI** <br/> |7 giugno Update- [https://support.microsoft.com/kb/3115087](https://support.microsoft.com/kb/3115087) <br/> |
|**Mac e iOS** <br/> |**Versione** <br/> |
||Client Skype for Business Mac versione 16,9  <br/> Client iOS Skype for Business versione 6,16  <br/> |
|**Android** <br/> |**Versione** <br/> |
||Client Android Skype for Business versione 6,17  <br/> |
|**Lync Phone Edition** <br/> |**Versione** <br/> |
|| Aastra 6721ip et Aastra 6725ip Phones-September 2016 Cumulative Update (Build 7577,4512)-[https://support.microsoft.com/kb/3194831](https://support.microsoft.com/kb/3194831) <br/> |
|| Telefoni HP 4110 e HP 4120-aggiornamento cumulativo di settembre 2016 (Build 7577,4512)-[https://support.microsoft.com/kb/3194832](https://support.microsoft.com/kb/3194832) <br/> |
||Polycom CX500, Polycom CX600 e Polycom CX3000 telefoni-September 2016 Cumulative Update (Build 7577,4512)- [https://support.microsoft.com/kb/3194833](https://support.microsoft.com/kb/3194833) <br/> |
   

