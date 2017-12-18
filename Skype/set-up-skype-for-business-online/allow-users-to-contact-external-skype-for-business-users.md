---
title: "Consentire agli utenti di contattare utenti Skype for Business esterni"
ms.author: TONYSMIT
author: tonysmit
manager: scotv
ms.date: 11/9/2017
ms.audience: Admin
ms.topic: article
f1_keywords:
- For O365M_ShareLync
- ms.lync.lac.OrgExternalAccess
- ms.lync.lac.skypefederation
- O365E_HRCLYNC _ SipFederationSrvRecordVerified_FL312122
- O365E_ShareLync
- O365M_ShareLync
- O365P_ExternalCommDesc
- O365P_ShareLync
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_Skype4B_Online
- Adm_Skype4B_Online_Top
- Adm_UI_Elements
ms.custom:
- Adm_O365_FullSet
- DianeF_Adm_Simplified
- LIL_Placement
ms.assetid: b414873a-0059-4cd5-aea1-e5d0857dbc94

description: "See how to configure Skype for Business to let users talk to users in another organization, or let outside contacts to them. "
---

# Consentire agli utenti di contattare utenti Skype for Business esterni

> [!IMPORTANT]
> Il presente articolo è stato tradotto automaticamente, vedere la dichiarazione di non responsabilità.  
  
> [!NOTE]
> Skype per la federazione Business non è disponibile in Office 365 gestito da 21Vianet e organizzazioni di Office 365 Germania. 
  
Segui la procedura di questo articolo nei seguenti casi: 
  
- Gli utenti della tua azienda appartengono a domini diversi, ad esempio Rob@ContosoEast.com e Ann@ContosoWest.com.
    
- Desideri che gli utenti della tua organizzazione usino Skype for Business per contattare persone di aziende specifiche all'esterno dell'organizzazione
    
- OPPURE vuoi che tutti quelli che usano Skype for Business possano trovarti e contattarti usando il tuo indirizzo e-mail. Se tu e loro usate le impostazioni predefinite di Skype for Business, questo avviene automaticamente. Altrimenti, devono assicurarsi che la loro configurazione non stia bloccando il tuo dominio.
    
## Abilitare la comunicazione tra aziende per gli utenti
<a name="bk_preview"> </a>

Per eseguire questa procedura, è necessario avere autorizzazioni di [Informazioni sui ruoli di amministratore di Office 365](about-office-365-admin-roles.md) in Office 365.
  
1. Accedere con l'account di amministratore Office 365.
    
2. In Interfaccia di amministrazione di Office 365, vai a **Interfacce di amministrazione** > **Skype for Business**. 
    
    ![Choose the Skype for Business admin center.](../images/376a7a45-e6e3-4716-be09-d2f294d885a2.png)
  
3. In **Interfaccia di amministrazione di Skype for Business**, scegliere **organizzazione** > **comunicazioni esterne**.
    
4. Per configurare le comunicazioni con una specifica azienda o con gli utenti in un altro dominio, nella casella di riepilogo a discesa, scegliere **in solo per i domini consentiti**.
    
    OPPURE, se vuoi consentire la comunicazione con chiunque altro nel mondo abbia politiche Skype for Business, scegli **Attiva eccetto i domini bloccati**. Questa è l'impostazione predefinita.
    
5. In **domini bloccati o consentiti**, scegliere **+** e aggiungere il nome del dominio che si desidera consentire.
    
6. Verificare che l'amministratore all'interno dell'organizzazione è gli stessi passaggi loro **Interfaccia di amministrazione di Skype for Business**. Ad esempio, nell'elenco **domini consentiti** amministratore deve immettere il dominio per l'azienda.
    
7. Se si utilizza Windows Firewall, Skype for Business apre automaticamente le porte necessarie. 
    
    Se l'organizzazione utilizza una soluzione firewall diverso per impedire che i computer della rete la connessione a Internet, assicurarsi che i computer client in grado di accedere seguenti [URL e intervalli di indirizzi IP per Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2). Questo potrebbe essere necessario aggiungere il FQDN a in uscita configurazione dell'infrastruttura di elenco nel firewall o proxy Consenti: ***. api.skype.com, *. users.storage.live.com e graph.skype.com**. Per istruzioni su come aprire le porte nel firewall, consultare la documentazione fornita in dotazione con essa.
    
    Per un elenco di tutte le porte, è necessario aprire, vedere [URL e intervalli di indirizzi IP per Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2#bkmk_lyo) nell'articolo[URL e intervalli di indirizzi IP per Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2).
    
8. **ATTENDERE fino a 24 ore per verificare**. Ogni volta che si modificano le impostazioni comunicazioni esterne, è possibile richiedere fino a 24 ore per le modifiche apportate a popolare tra tutte le aree di dati.
    
![Skype](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) È possibile consentire agli utenti di cercare e la messaggistica Istantanea con chiunque utilizzi Skype, l'app gratuita consumer! Per ulteriori informazioni, vedere[Consenti agli utenti di Skype for Business di aggiungere contatti Skype](let-skype-for-business-users-add-skype-contacts.md).
  
## Test e risoluzione dei problemi
<a name="bk_preview"> </a>

 **Il problema più comune persone affrontano quando si configura la comunicazione business-to-business riceveranno le [URL e intervalli di indirizzi IP per Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) destra.**
  
Per testare la configurazione, è necessario un contatto Skype for Business che non si trova all'interno del firewall aziendale.
  
1. Dopo aver modificato le impostazioni di comunicazione esterna, **ASPETTA FINO A 24 ORE PER TESTARLE**.
    
2. In Skype for Business, cerca il tuo contatto in Skype for Business, e invia una richiesta di chat. 
    
    Se viene visualizzato un messaggio che non è stato inviato a causa di criteri aziendali, è necessario controlla le [URL e intervalli di indirizzi IP per Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2).
    
3. Chiedi al tuo contatto Skype for Business di inviarti una richiesta di chat. Se non ricevi la sua richiesta, il problema sono le tue impostazioni del firewall (sempre che il tuo contatto abbia confermato che le sue impostazioni del firewall sono corrette). 
    
4. Un altro modo per verificare se il problema è il firewall consiste nel passare a una località wifi non all'interno del firewall, ad esempio un bar e utilizzare Skype for Business per inviare una richiesta al contatto alla chat. Se il messaggio attraversa sono, ma non quando si è in ufficio, si conosce il problema è il firewall.
    
## Come trovare gli altri, ed essere trovati, quando ti colleghi con un'altra azienda
<a name="bk_preview"> </a>

Dopo aver attivato le comunicazioni esterne con altri utenti di Skype for Business, gli utenti possono trovare utenti federati Skype for Business cercandone il proprio nome di accesso: ad esempio Rob@contoso.com. Quindi vengono sarà necessario aggiungere l'utente al proprio elenco dei contatti.
  
![To find a user in a federated business, you must search for their email address (this is usally also their sign in name).](../images/20242f85-0636-463b-8df3-1e123784d7fa.png)
  
## Suggerimenti per la configurazione delle comunicazioni con le aziende federate
<a name="bk_preview"> </a>

- Per configurare la federazione tra Skype for Business 2015 e Skype for Business Online, consulta questo articolo TechNet: [Configurare la federazione con Skype for Business Online](https://technet.microsoft.com/en-us/library/jj205126.aspx).
    
- Per configurare la federazione tra Lync e Skype for Business Online, consulta questo articolo TechNet: [Configurazione del supporto della federazione per un cliente di Lync Online](https://technet.microsoft.com/en-us/library/hh202193.aspx).
    
- Quando due utenti Skype for Business in Office 365 comunicano tra loro in domini separati, possono utilizzare solo le funzionalità di Skype for Business (ad esempio, conversazioni video o condivisione desktop) abilitate in entrambe le organizzazioni. 
    
- Se un utente Skype for Business all'interno dell'organizzazione viene inserito in un posto o tenere controversie legali, le conversazioni di messaggistica Istantanea tra l'utente e altre Skype for Business o gli utenti Skype verranno salvate **Gli elementi recuperati** nella propria cassetta postale. Le conversazioni non vengono salvate nella cartella **Cronologia conversazioni** nella propria cassetta postale.
    
## Disabilitare la comunicazione esterna per individui specifici
<a name="bk_preview"> </a>

Una volta abilitata la comunicazione esterna per l'intera azienda, puoi disabilitarla solo per individui specifici. 
  
1. Accedere con l'account di amministratore Office 365.
    
2. Nella Interfaccia di amministrazione di Office 365, accedi a **utenti** > **utenti attivi**.
    
3. Nell'elenco degli utenti, fai clic sull'utente, quindi in **Altre impostazioni** fai clic su **Modifica proprietà Skype for Business**.
    
    ![Choose Skype for Business](../images/2b0f9a7b-3fee-4f4b-968a-68c429eeb395.png)
  
4. Scegliere **le comunicazioni esterne** di **Skype per Business admin center**.
    
    Nella pagina delle **Opzioni**, tutte le opzioni verrà selezionate. Deselezionare le comunicazioni che si desidera disattivare. Nella figura seguente mostra che Jakob saranno in grado di comunicare con utenti di altre aziende attendibile, ma non con altri utenti di Skype.
    
    ![Choose External contacts](../images/4e546321-a065-48ed-8ac7-1e112a780eab.png)
  
5. Scegliere **Save**.
    
> [!NOTE]
> Per rendere effettive le modifiche potrebbero essere necessarie fino a 24 ore. 
  
## 
<a name="bk_preview"> </a>

 *Ultimo aggiornamento dell'articolo: 23 marzo 2017* 
  
## 
<a name="bk_preview"> </a>

||
|:-----|
|![Icona breve di LinkedIn Learning.](../images/7e5cb7c8-dc66-4c9a-a16d-a30f10a970bd.png) **Nuovi utenti di Office 365?**         Vedere i corsi video gratuiti per **amministratori di Office 365 e professionisti IT**, offerti da LinkedIn Learning. |
   
## Argomenti correlati
<a name="bk_preview"> </a>

[Configurare Skype for Business online](set-up-skype-for-business-online.md)
  
[Consenti agli utenti di Skype for Business di aggiungere contatti Skype](let-skype-for-business-users-add-skype-contacts.md)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Dichiarazione di non responsabilità per la traduzione automatica**: Il presente articolo è stato tradotto tramite un software di traduzione automatica e non da una persona. Microsoft offre le traduzioni automatiche per consentire a coloro che non conoscono la lingua inglese di leggere gli articoli sui prodotti, sui servizi e sulle tecnologie Microsoft. Dal momento che l'articolo è stato tradotto automaticamente, potrebbe contenere errori di sintassi, di grammatica o di utilizzo dei vocaboli. 
  

