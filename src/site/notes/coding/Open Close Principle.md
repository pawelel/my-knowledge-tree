---
{"title":"Open Close Principle","dg-publish":true,"tags":"coding/SOLID","language":"en","permalink":"/coding/open-close-principle/","dgPassFrontmatter":true}
---

up:: [[coding/SOLID\|SOLID]]
alt:: [[coding/Reguła Otwarte zamknięte\|Reguła Otwarte zamknięte]]
Open Close Principle means that the modules should be open for extensions, but closed for modifications. To achieve this, instead of using multiple methods, you can implement interface.
```cs
public class InvoicePersistance
{
	private Invoice _invoice;
	private IInvoiceSaver _invoiceSaver;

	public Invoice(Invoice invoice, IInvoiceSaver invoiceSaver) {
		_invoice = invoice;
		_invoiceSaver = invoiceSaver;
	}
	_invoiceSaver.Save(_invoice);
}
```

