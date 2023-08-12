# Test
Just a test to understand 
import pdfplumber

def estrai_testo(pdf_path):
    testo_completo = ''
    
    with pdfplumber.open(pdf_path) as pdf:
        for pagina in pdf.pages:
            testo = pagina.extract_text()
            if testo:
                testo_completo += testo + '\n'

    return testo_completo

pdf_path = 'path_del_tuo_file.pdf'
testo = estrai_testo(pdf_path)
print(testo)
