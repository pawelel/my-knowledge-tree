---
{"title":"Open Close Principle","dg-publish":true,"tags":"coding/SOLID","permalink":"/coding/open-close-principle/","dgPassFrontmatter":true}
---

up:: [[coding/SOLID\|SOLID]]

## EN

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

## PL

Reguła polega na tym, że  aplikacja jest otwarta na rozszerzenia, ale zamknięta na modyfikacje. Dzięki temu kod może być łatwiejszy w urzymaniu.

Zasada przypomina korzystanie z wtyczek - bez konieczności modyfikacji kodu możliwe jest dodanie rozszerzeń.