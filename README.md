# PyMT-mouse-scRNA-seq
Expression matrix and metadata for PyMT mouse RNA-seq
The seurat object to export expression matrix and meta data for you was used in figure1 of our paper (https://www.nature.com/articles/s41419-021-04261-y).
This object comprised Lin- epithelium cells (CD31−CD140b−CD45−) and CD45+ immune cells (CD31−CD140b−CD45+).

The code used to export expression matrix and meta data was below:

##############

exprs.matrix = GetAssayData(object = bc, slot = "counts")

write.table(exprs.matrix, file = "BC.exprs.matrix.txt", sep = "\t", quote = F)

write.table(bc@meta.data, file = 'BC.meta.data.txt', sep = "\t", quote = F)

##############

There are four levels in “orig.ident” of meta data, Y07, Y09, Y11 and Y17 which represent cells from week 7, 9 , 11 and 17, respectively.
Additionally, we also exported the name of cells into "BC.exprs.matrix.cell.title.txt", since the number prefix of the cell name in expression matrix file were converted to X.

