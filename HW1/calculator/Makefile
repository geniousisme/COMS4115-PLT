objs = parser.cmo scanner.cmo calc.cmo

all: scanner.ml parser.ml parser.mli ast.cmi parser.cmi scanner.cmo parser.cmo calc.cmo calc

parser.ml parser.mli:
	ocamlyacc parser.mly

%.cmi: %.mli
	ocamlc -c $<

%.cmo: %.ml
	ocamlc -c $<

scanner.ml: scanner.mll
	ocamllex $<

calc: $(objs)
	ocamlc -o calc $(objs)

clean:
	rm -f calc parser.ml parser.mli scanner.ml *.cmo *.cmi