---
title: Pianificare più numeri di emergenza in Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
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
ms.custom: null
ms.assetid: 5ed45a22-ddf0-419f-84da-895a73df855f
description: Leggere questo argomento per informazioni su come pianificare più numeri di emergenza in Skype for Business Server.
---

# <a name="plan-for-multiple-emergency-numbers-in-skype-for-business-server"></a>Pianificare più numeri di emergenza in Skype for Business Server
 
Leggere questo argomento per informazioni su come pianificare più numeri di emergenza in Skype for Business Server.
  
Skype for Business Server ora supporta la configurazione di più numeri di emergenza per un client. Più numeri di emergenza è una nuova funzionalità introdotta nell'aggiornamento cumulativo di giugno 2016. Mentre gli Stati Uniti hanno un unico numero di emergenza, 911, molti paesi supportano più numeri di emergenza. Il Regno Unito, ad esempio, supporta sia il 999, il numero di emergenza specifico per il Regno Unito, sia il 112, il numero di emergenza per l'Unione europea. 
  
Questa funzionalità è utile anche per i provider di servizi sanitari negli Stati Uniti che desiderano disporre del supporto per il roaming per più codici di emergenza blu.
  
## <a name="multiple-emergency-numbers-and-location-policies"></a>Più numeri di emergenza e criteri percorso

È possibile configurare le chiamate di emergenza creando criteri percorso che definiscono la modalità di implementazione delle chiamate di emergenza. Il criterio percorso viene utilizzato per definire il numero che costituisce una chiamata di emergenza, ad esempio 911 negli Stati Uniti. 999 e 112 nel Regno Unito. Il criterio percorso determina se un utente è abilitato per le chiamate di emergenza e, in tal caso, qual è il comportamento di una chiamata di emergenza. È inoltre possibile definire se la sicurezza aziendale deve essere notificata automaticamente e come instradare la chiamata.
  
Per ulteriori informazioni sulla definizione e la modifica di un criterio percorso, vedere [Plan location policies for Skype for Business Server](location-policies.md) e [Create location policies in Skype for Business Server](../../deploy/deploy-enterprise-voice/create-location-policies.md). Questi argomenti descrivono i concetti relativi ai criteri percorso. Tuttavia, è necessario seguire le istruzioni in [Configurare più numeri](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md) di emergenza in Skype for Business per configurare più numeri di emergenza.
  
Quando si pianificano più numeri di emergenza, tenere presente quanto segue:
  
- Con l'aggiornamento cumulativo di giugno 2016, è possibile definire fino a 5 numeri di emergenza per un determinato criterio percorso. Con l'aggiornamento cumulativo di novembre 2016, questo numero aumenta a 100.
    
    > [!NOTE]
    > Se non è stato ancora eseguito l'aggiornamento cumulativo di novembre 2016, vedere [Updates to Skype for Business Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015). 
  
- Per ogni numero di emergenza, è possibile specificare zero o più maschere di composizione di emergenza, che sono univoche per un determinato criterio di posizione.
    
    Una maschera di composizione è un numero che si desidera convertire nel valore del numero di chiamata di emergenza quando viene composto. Si supponga ad esempio di immettere un valore pari a 212 in questo campo e che il campo numero di chiamata di emergenza abbia un valore pari a 911. Quando un utente compone il numero 212, il numero viene convertito in 911. Ciò consente di comporre numeri di emergenza alternativi e di avere comunque i servizi di emergenza per raggiungere la chiamata (ad esempio, se un utente di un paese o di un'area geografica con un numero di emergenza diverso tenta di comporre il numero del paese o dell'area geografica anziché il numero del paese o dell'area geografica in cui si trova). È possibile definire più maschere di composizione del numero di emergenza separando i valori con un punto e virgola. Ad esempio, 212;414. Il limite di stringa per una maschera di composizione è di 100 caratteri. Ogni carattere deve essere costituito da una cifra compresa tra 0 e 9.
    
- Ogni criterio percorso dispone di un singolo utilizzo PSTN (Public Switched Telephone Network) utilizzato per determinare quale route vocale viene utilizzata per instradare le chiamate di emergenza dai client che utilizzano questo criterio. L'utilizzo può avere una route univoca per ogni numero di emergenza.
    
- Se per un criterio percorso sono definiti entrambi i parametri EmergencyNumbers e DialString e il client supporta più numeri di emergenza, il numero di emergenza ha la precedenza. Se il client non supporta più numeri di emergenza, viene utilizzata la stringa di composizione di emergenza.
    
- Per informazioni su quali client Skype for Business e Lync supportano la ricezione di più numeri di emergenza, maschere di chiamata e utilizzi PSTN (Public Switched Telephone Network), vedere [Client support](multiple-emergency-numbers.md#BKMK_Clients).
    
> [!NOTE]
> Non è possibile configurare più numeri di emergenza utilizzando il Skype for Business pannello di controllo. È necessario utilizzare PowerShell per configurare più numeri di emergenza. 
  
Prima di configurare più numeri di emergenza, tenere presente quanto segue:
  
- Per configurare più numeri di emergenza, è necessario utilizzare il cmdlet New-CsEmergencyNumber ed è necessario definire criteri percorso che supportano più numeri di emergenza specificando il parametro EmergencyNumbers con i cmdlet [New-CsLocationPolicy](/powershell/module/skype/new-cslocationpolicy?view=skype-ps) e [Set-CsLocationPolicy](/powershell/module/skype/set-cslocationpolicy?view=skype-ps) .
    
- Se sono stati definiti numeri esistenti utilizzando il cmdlet Set-CsLocationPolicy o New-CsLocationPolicy con i parametri EmergencyDialString e EmergencyDialMask, i valori specificati con il parametro EmergencyNumbers avranno la precedenza sui valori precedenti. In altri parole, i valori per i parametri EmergencyDialString e EmergencyDialMask verranno ignorati.
    
- Se sono stati definiti numeri esistenti utilizzando il cmdlet Set-CsLocationPolicy o New-CsLocationPolicy con i parametri EmergencyDialString e EmergencyDialMask e non si configurano nuovi numeri di  *emergenza, i*  numeri esistenti continueranno a essere utilizzati.
    
- Per il funzionamento della funzionalità con più numeri di emergenza, le versioni client in esecuzione devono essere in grado di supportare la nuova funzionalità. I client meno recenti continueranno a utilizzare i valori precedenti specificati dai cmdlet Set-CsLocationPolicy o New-CsLocationPolicy con i parametri EmergencyDialString e EmergencyDialMask. 
    
- Se gli utenti componeranno un numero corrispondente alla stringa di composizione, non è necessaria alcuna maschera di composizione. Ad esempio, se il numero composto da un utente è 911, la stringa di composizione sarà 911 e non sarà necessaria alcuna maschera. 
    
Per ulteriori informazioni sulla configurazione di più numeri di emergenza, vedere [Configure multiple emergency numbers in Skype for Business](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md).
  
Nella tabella seguente vengono illustrati criteri percorso di esempio (ai fini dell'esempio, non vengono visualizzati tutti gli attributi):
  

|**Nome criterio percorso**|**E911 abilitato**|**Stringa di composizione per gli interventi di emergenza**|**Maschera di composizione**|**Numeri di emergenza**|**Utilizzo PSTN**|**Percorso necessario**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Stati Uniti  <br/> |Sì  <br/> |911  <br/> | 112;999 <br/> ||USEmergency  <br/> |Sì  <br/> |
|US-Hospital  <br/> |Sì  <br/> |911  <br/> |450  <br/> |911  <br/> 450  <br/> |SeattleEmergency  <br/> |Sì  <br/> |
|Londra  <br/> |Sì  <br/> |999  <br/> |144  <br/> |999-144  <br/> 112-911;117;118  <br/> |GBEmergency  <br/> |No  <br/> |
|India  <br/> |Sì  <br/> |||100-911  <br/> 101  <br/> 102  <br/> |IndiaEmergency  <br/> |No  <br/> |
   
 **Stati Uniti** : non è necessario utilizzare più numeri di emergenza. Negli Stati Uniti, si utilizzano le vecchie configurazioni di stringa di composizione di emergenza e maschera di composizione.
  
 **US-Hospital** : è necessario non mascherare "450". Per i client che non supportano ancora più numeri di emergenza, è possibile utilizzare le vecchie configurazioni di stringa di composizione di emergenza e maschera di chiamata. Per i client che supportano più numeri di emergenza, è possibile definire un numero di emergenza sia per "911" che per "450" anziché mascherare 450.
  
 **Londra** : per i client che non supportano ancora più numeri di emergenza, è possibile utilizzare le vecchie configurazioni della stringa di composizione di emergenza e della maschera di chiamata. Per i client che supportano più numeri di emergenza, è possibile definire un numero di emergenza sia per "999" che per "112" con maschere per ognuno di essi.
  
 **India** : tutti i client distribuiti supportano più numeri di emergenza. In India, è necessario configurare solo più numeri di emergenza.
  
## <a name="client-support"></a>Supporto client
<a name="BKMK_Clients"> </a>

La tabella seguente mostra il supporto client per più numeri di emergenza. Microsoft continuerà a testare e rilasciare il supporto per altri client. Controllare nuovamente in seguito.

|**Windows**|**Versione**|
|:-----|:-----|
|**A portata di clic** <br/> |CC (Current Channel) rilasciato il 10 maggio 2016 - Versione 1604 (Build 6868.2062)  <br/> |
||FRDC (First Release Current Channel) rilasciato il 14 giugno 2016 - Versione 1605 (Build 6965.2058)  <br/> |
||DC (Deferred Channel) rilasciato l'11 ottobre 2016 - Versione 1605 (Build 6965.2092)  <br/> |
|**MSI** <br/> |Aggiornamento del 7 giugno - [https://support.microsoft.com/kb/3115087](https://support.microsoft.com/kb/3115087) <br/> |
|**Mac e iOS** <br/> |**Versione** <br/> |
||Skype for Business client Mac versione 16.9  <br/> Skype for Business client iOS versione 6.16  <br/> |
|**Android** <br/> |**Versione** <br/> |
||Skype for Business client Android versione 6.17  <br/> |
|**Lync Phone Edition** <br/> |**Versione** <br/> |
|| Telefoni Aastra 6721ip e Aastra 6725ip - Aggiornamento cumulativo di settembre 2016 (Build 7577.4512) -[https://support.microsoft.com/kb/3194831](https://support.microsoft.com/kb/3194831) <br/> |
|| Telefoni HP 4110 e HP 4120 - Aggiornamento cumulativo di settembre 2016 (Build 7577.4512) -[https://support.microsoft.com/kb/3194832](https://support.microsoft.com/kb/3194832) <br/> |
||Telefoni Polycom CX500, Polycom CX600 e Polycom CX3000 - Aggiornamento cumulativo di settembre 2016 (Build 7577.4512) - [https://support.microsoft.com/kb/3194833](https://support.microsoft.com/kb/3194833) <br/> |
