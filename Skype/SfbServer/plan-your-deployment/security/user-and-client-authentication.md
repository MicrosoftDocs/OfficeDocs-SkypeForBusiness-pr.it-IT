---
title: Autenticazione utente e client per Skype for Business Server
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
ms.assetid: 77f4b62a-f75c-424d-8f02-a6519090015d
description: Un utente attendibile è colui le cui credenziali sono state autenticate da un server attendibile in Skype for Business Server. Questo server è in genere un server Standard Edition, un server front-end Enterprise Edition o un Director. Skype for Business Server si basa su servizi di dominio Active Directory come singolo repository back-end attendibile delle credenziali utente.
ms.openlocfilehash: 2ffabce6546bf8b542503f8c80fe5cb2b952c568
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815584"
---
# <a name="user-and-client-authentication-for-skype-for-business-server"></a>Autenticazione utente e client per Skype for Business Server
 
Un utente attendibile è colui le cui credenziali sono state autenticate da un server attendibile in Skype for Business Server. Questo server è in genere un server Standard Edition, un server front-end Enterprise Edition o un Director. Skype for Business Server si basa su servizi di dominio Active Directory come singolo repository back-end attendibile delle credenziali utente.
  
L'autenticazione è la fornitura di credenziali utente a un server attendibile. Skype for Business Server usa i protocolli di autenticazione seguenti, a seconda dello stato e della posizione dell'utente.
  
- **Protocollo di sicurezza Kerberos versione 5 mit** per gli utenti interni con credenziali di Active Directory. Kerberos richiede la connettività client ai servizi di dominio Active Directory, motivo per cui non può essere usato per l'autenticazione dei client esterni al firewall aziendale.
    
- **Protocollo NTLM** per gli utenti con le credenziali di Active Directory che si connettono da un endpoint esterno al firewall aziendale. Il servizio Access Edge passa le richieste di accesso a un amministratore, se presente, o a un server front-end per l'autenticazione. Il servizio Access Edge non esegue alcuna autenticazione.
    
    > [!NOTE]
    > Il protocollo NTLM offre una protezione dagli attacchi più debole rispetto a Kerberos, in modo che alcune organizzazioni riducano l'uso di NTLM. Di conseguenza, l'accesso a Skype for Business Server potrebbe essere limitato a utenti interni o client connessi tramite una connessione VPN o DirectAccess. 
  
- **Protocollo digest** per i cosiddetti utenti anonimi. Gli utenti anonimi sono utenti esterni che non hanno credenziali Active Directory riconosciute, ma che sono stati invitati a una conferenza locale e possiedono una chiave di conferenza valida. L'autenticazione digest non viene utilizzata per altre interazioni client.
    
L'autenticazione di Skype for Business Server è costituita da due fasi:
  
1. Viene stabilita un'associazione di protezione tra il client e il server.
    
2. Il client e il server utilizzano l'associazione di protezione esistente per firmare i messaggi inviati e per verificare i messaggi ricevuti. I messaggi non autenticati da un client non vengono accettati quando l'autenticazione è abilitata sul server.
    
L'attendibilità dell'utente è associata a ciascun messaggio che proviene da un utente, non all'identità dell'utente stesso. Il server verifica che ogni messaggio abbia credenziali utente valide. Se le credenziali utente sono valide, il messaggio non viene contestato solo dal primo server per riceverlo, ma da tutti gli altri server nel cloud del server trusted.
  
Gli utenti con credenziali valide emesse da un partner federato sono attendibili ma opzionalmente limitati da vincoli aggiuntivi per cui non possono usufruire dell'intera gamma di privilegi concessi agli utenti interni.
  
I protocolli ICE e TURN usano anche la sfida digest come descritto in IETF TURN RFC.
  
I certificati client rappresentano un modo alternativo per consentire agli utenti di essere autenticati da Skype for Business Server. Anziché fornire un nome utente e una password, gli utenti hanno un certificato e la chiave privata corrispondente al certificato necessario per risolvere un'autenticazione crittografica. Questo certificato deve avere un nome soggetto o un nome alternativo soggetto che identifichi l'utente e debba essere emesso da una CA radice considerata attendibile dai server che hanno eseguito Skype for Business Server, entro il periodo di validità del certificato e non sono stati revocati. Per essere autenticati, gli utenti devono digitare solo un PIN (Personal Identification Number). I certificati sono particolarmente utili per telefoni cellulari e altri dispositivi in cui è difficile immettere un nome utente e una password.
  
### <a name="cryptographic-requirements-due-to-asp-net-45"></a>Requisiti crittografici a causa di ASP .NET 4,5 

A partire da Skype for Business Server 2015 CU5, AES non è supportato per ASP.NET 4,6 e potrebbe non essere possibile avviare l'app riunioni Skype. Se un client usa AES come valore di convalida della chiave del computer, dovrai reimpostare il valore della chiave del computer su SHA-1 o su un altro algoritmo supportato nel livello del sito dell'app riunioni Skype su IIS. Se necessario, vedere [gestione della configurazione di IIS 8,0 ASP.NET](https://docs.microsoft.com/iis/get-started/whats-new-in-iis-8/iis-80-aspnet-configuration-management) per le istruzioni.
  
Altri valori supportati sono:
  
- HMACSHA256
    
- HMACSHA384
    
- HMACSHA512
    
  I valori AES, 3DES e MD5 non sono più consentiti, dato che erano in ASP.NET 4. I [miglioramenti crittografici in ASP.NET 4,5, PT. 2](https://blogs.msdn.microsoft.com/webdev/2012/10/23/cryptographic-improvements-in-asp-net-4-5-pt-2/) sono più dettagli.
  
