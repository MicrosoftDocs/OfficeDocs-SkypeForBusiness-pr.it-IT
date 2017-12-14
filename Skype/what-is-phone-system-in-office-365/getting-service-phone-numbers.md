---
title: "Recupero di numeri di telefono di servizio Skype for Business"
ms.author: tonysmit
author: tonysmit
ms.date: 11/14/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.custom: Strat_SB_PSTN
ms.assetid: e434aeb2-af99-40e7-981e-a474f0383734

description: "Oltre a ottenere numeri di telefono per singoli utenti di Office 365, è anche possibile cercare e acquisire numeri di telefono a tariffa o gratuiti (numeri verdi) per servizi come le conferenze con accesso esterno (per il bridging delle conferenze) e operatori automatici che sono numeri di servizio da chiamare. I numeri di servizio hanno una capacità di chiamate contemporanee superiore ai numeri di telefono per utenti o abbonati. Ad esempio, un numero di servizio può gestire centinaia di chiamate simultanee, mentre il numero di un utente può gestire solo alcune chiamate simultanee."
---

# Recupero di numeri di telefono di servizio Skype for Business

Oltre a ottenere numeri di telefono per singoli utenti di Office 365, è anche possibile cercare e acquisire numeri di telefono a tariffa o gratuiti (numeri verdi) per servizi come le conferenze con accesso esterno (per il bridging delle conferenze) e operatori automatici che sono numeri di servizio da chiamare. I numeri di servizio hanno una capacità di chiamate contemporanee superiore ai numeri di telefono per utenti o abbonati. Ad esempio, un numero di servizio può gestire centinaia di chiamate simultanee, mentre il numero di un utente può gestire solo alcune chiamate simultanee.
  
> [!IMPORTANT]
> Deve prima essere configurata la tariffa PSTN a consumo per poter acquisire numeri verdi. 
  
Ci sono due modi per ottenere numeri di servizio da usare con Skype for Business: 
  
- Ottenere numeri di telefono da Office 365 e Skype for Business.
    
- Trasferire i numeri di telefono esistenti dal provider di servizi o dal gestore di telefonia
    
    > [!NOTE]
    > Quando trasferisci i numeri di servizio, consigliamo caldamente di contattare l'[Contattare il supporto di Office 365 per le aziende - Guida per gli amministratori](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) per assicurarti che la maggiore capacità di chiamate contemporanea sia stata considerata e configurata correttamente.
  
## Ottenere i numeri di servizio

1. Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.
    
2. Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.
    
3. Nella barra di spostamento sinistra, passa a **Voce** > **Numeri di telefono** > **e** quindi fai clic su **Nuovi numeri di servizio**.
    
    **IMPORTANTE**: per visualizzare l'opzione **Voce** nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Skype for Business, è necessario acquistare almeno una **licenza Enterprise E5**, una licenza per il componente aggiuntivo **Sistema telefonico** o una licenza per il componente aggiuntivo **Audioconferenza**.
    
4. Nella pagina **Aggiungi nuovi numeri utente**, fai clic sull'elenco a discesa nella sezione per selezionare:
    
  - **Paese/area geografica**
    
  - **Stato/regione**
    
  - **Città**
    
5.  In **Quantità**, inserisci quanti numeri di telefono vuoi impostare per l'organizzazione, quindi fai clic su **Aggiungi** per creare una prenotazione. Hai 10 minuti di tempo per selezionare i numeri di telefono. Se superi i 10 minuti, i numeri di telefono verranno restituiti nel pool di numeri.
    
    > [!NOTE]
    > Puoi visualizzare quanti numeri di telefono puoi acquisire in base al numero di licenze di cui disponi in **Totale numeri utente che è possibile acquisire**. 
  
6. Facendo clic su **Mostra numeri** puoi visualizzare l'elenco completo dei numeri di telefono. Questa funzionalità è utile se non desideri selezionare un numero di telefono specifico incluso nell'elenco.
    
7. Seleziona i numeri di telefono desiderati e quindi fai clic su **Acquisisci numeri**.
    
### Assegnare i numeri di servizio

Una volta ottenuti, i numeri di servizio possono essere assegnati a un bridge per conferenza telefonica con accesso esterno. Per farlo, consulta [Modificare il numero verde o numeri a pagamento gratuito il bridge di conferenze Audio](../audio-conferencing-in-office-365/change-the-toll-or-toll-free-numbers-on-your-audio-conferencing-bridge.md).
  
### Portabilità o trasferimento dei numeri di servizio

Se voi trasferire numeri di servizio esistenti dall'operatore o provider di servizio attuale, devi presentare manualmente un ordine di portabilità a Microsoft. Dovrai inviare ordini di trasferimento separati per ogni tipo di numero di telefono (a tariffa o numero verde) che intendi trasferire mediante una lettera di autorizzazione (LOA, Letter of Authorization). Nella lettera di autorizzazione devi selezionare il tipo corretto di numero di servizio. Quando contatti l'assistenza Microsoft, assicurati di specificare che stai trasferendo un numero di servizio ( *e non un numero utente o abbonato*  ), altrimenti la capacità di chiamate contemporanee potrebbe essere insufficiente per gestire volumi elevati di chiamate. Per saperne di più su una richiesta di ordine di portabilità inviata, consulta[Inviare manualmente una richiesta di servizio](../what-are-calling-plans-in-office-365/manually-submit-a-custom-service-request.md)
  
## Espandi per visualizzare quanti numeri di telefono puoi ottenere.

Se per la tua organizzazione hai bisogno di numeri di telefono aggiuntivi, puoi ottenere una quantità di numeri di telefono maggiore rispetto al numero di licenze assegnate. Tutto dipende, però, dal tipo di numeri di telefono e di licenze acquistate e assegnate.
  
Puoi vedere quanti numeri di telefono puoi ottenere nella pagina **Numeri di telefono** nell'interfaccia di amministrazione Skype for Business oppure puoi eseguire il cmdlet[Get-CsOnlineTelephoneNumberAvailableCount](https://technet.microsoft.com/en-us/library/mt634605.aspx). 
  
> [!IMPORTANT]
> I limiti seguenti non includono i numeri di telefono trasferiti su Microsoft. 
  
||||
|:-----|:-----|:-----|
|**Ecco il tipo di numero di telefono** <br/> |**Come ottieni i numeri di telefono totali?** <br/> |**Ecco un esempio** <br/> |
|Numero dell'utente (abbonato)  <br/> |La quantità di numeri di telefono è uguale al numero totale delle licenze del piano di chiamate vocali  *nazionali + nazionali e internazionali*  moltiplicato per 1,1 + 10 numeri di telefono aggiuntivi che vengono assegnati. <br/> |In caso di un numero totale di utenti pari a 50 con piani per le chiamate vocali sia nazionali che nazionali e internazionali, puoi acquisire **65** numeri di telefono **(50 x 1,1 + 10)**. <br/> |
|Numero di servizio a pagamento  <br/> | La quantità di numeri di telefono è pari al numero totale di licenze per *Cloud PBX + servizi di conferenza PSTN*  e viene calcolata in base a quanto segue: <br/>  Se sono disponibili **da 1 a 25 licenze** vengono assegnati **5** numeri di telefono. <br/>  Se sono disponibili **da 26 a 49 licenze** vengono assegnati **10** numeri di telefono. <br/>  Se sono disponibili **da 50 a 99 licenze** vengono assegnati **20** numeri di telefono. <br/>  Se sono disponibili **da 100 a 149 licenze** vengono assegnati **30** numeri di telefono. <br/>  Se sono disponibili **da 150 a 199 licenze** vengono assegnati **40** numeri di telefono. <br/>  Se sono disponibili **da 200 a 499 licenze** vengono assegnati **65** numeri di telefono. <br/>  Se sono disponibili **da 500 a 749 licenze** vengono assegnati **90** numeri di telefono. <br/>  Se sono disponibili **da 750 a 999 licenze** vengono assegnati **110** numeri di telefono. <br/>  Se sono disponibili **da 1000 a 1249 licenze** vengono assegnati **125** numeri di telefono. <br/>  Se sono disponibili **da 1250 a 1499 licenze** vengono assegnati **135** numeri di telefono. <br/>  Se sono disponibili **da 1500 a 1999 licenze** vengono assegnati **160** numeri di telefono. <br/>  Se sono disponibili **da 2000 a 2999 licenze** vengono assegnati **210** numeri di telefono. <br/>  Se sono disponibili **da 3000 a 6999 licenze** vengono assegnati **420** numeri di telefono. <br/>  Se sono disponibili **da 7000 a 9999 licenze** vengono assegnati **500** numeri di telefono. <br/>  Se sono disponibili **da 10.000 a 14.999 licenze** vengono assegnati **600** numeri di telefono. <br/>  Se sono disponibili **da 15.000 a 19.999 licenze** vengono assegnati **700** numeri di telefono. <br/>  Se sono disponibili **da 20.000 a 49.999 licenze** vengono assegnati **1000** numeri di telefono. <br/>  Se sono disponibili **più di 50.000 licenze** vengono assegnati **1500** numeri di telefono. <br/> |Con un totale di **51** licenze per Cloud PBX e servizio di conferenza PSTN puoi ottenere **20** numeri di servizio a pagamento. <br/> |
| Numero di servizio gratuito <br/> | La quantità di numeri di telefono è pari al numero totale di licenze per *Cloud PBX + servizi di conferenza PSTN*  e viene calcolata in base a quanto segue: <br/>  Se sono disponibili **da 1 a 25 licenze** vengono assegnati **5** numeri di telefono. <br/>  Se sono disponibili **da 26 a 49 licenze** vengono assegnati **10** numeri di telefono. <br/>  Se sono disponibili **da 50 a 99 licenze** vengono assegnati **20** numeri di telefono. <br/>  Se sono disponibili **da 100 a 149 licenze** vengono assegnati **30** numeri di telefono. <br/>  Se sono disponibili **da 150 a 199 licenze** vengono assegnati **40** numeri di telefono. <br/>  Se sono disponibili **da 200 a 499 licenze** vengono assegnati **65** numeri di telefono. <br/>  Se sono disponibili **da 500 a 749 licenze** vengono assegnati **90** numeri di telefono. <br/>  Se sono disponibili **da 750 a 999 licenze** vengono assegnati **110** numeri di telefono. <br/>  Se sono disponibili **da 1000 a 1249 licenze** vengono assegnati **125** numeri di telefono. <br/>  Se sono disponibili **da 1250 a 1499 licenze** vengono assegnati **135** numeri di telefono. <br/>  Se sono disponibili **da 1500 a 1999 licenze** vengono assegnati **160** numeri di telefono. <br/>  Se sono disponibili **da 2000 a 2999 licenze** vengono assegnati **210** numeri di telefono. <br/>  Se sono disponibili **da 3000 a 6999 licenze** vengono assegnati **420** numeri di telefono. <br/>  Se sono disponibili **da 7000 a 9999 licenze** vengono assegnati **500** numeri di telefono. <br/>  Se sono disponibili **da 10.000 a 14.999 licenze** vengono assegnati **600** numeri di telefono. <br/>  Se sono disponibili **da 15.000 a 19.999 licenze** vengono assegnati **700** numeri di telefono. <br/>  Se sono disponibili **da 20.000 a 49.999 licenze** vengono assegnati **1000** numeri di telefono. <br/>  Se sono disponibili **più di 50.000 licenze** vengono assegnati **1500** numeri di telefono. <br/> |Con un totale di **1001** licenze per Cloud PBX e servizio di conferenza PSTN puoi ottenere **125** numeri di servizio gratuiti. <br/> > [!IMPORTANT]> Per riservare e utilizzare i numeri verdi, è richiesta la [Configurare i Crediti comunicazioni per la propria organizzazione](../skype-for-business-and-microsoft-teams-add-on-licensing/set-up-communications-credits-for-your-organization.md).           |
   
> [!NOTE]
> Se hai bisogno di ulteriori numeri di telefono, visita la pagina [Contattare il supporto di Office 365 per le aziende - Guida per gli amministratori](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b). 
  
## Argomenti correlati

[Termini e condizioni per le chiamate al numero di emergenza](../what-are-calling-plans-in-office-365/emergency-calling-terms-and-conditions.md)
  
[Periodo di chiamata in uscita di conferenze audio](../accessibility-and-regulatory/audio-conferencing-complimentary-dial-out-period.md)
  

