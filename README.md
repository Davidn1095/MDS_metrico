# MDS_metrico

# Load the data from a file
datos <- read.table("european_cities1.dat", header = TRUE, sep = "", quote = "")

# Convert the data into a distance matrix
eurociti <- as.dist(datos)

# Perform classical multidimensional scaling (MDS)
result_cmdscale <- cmdscale(eurociti, k = 9, eig = TRUE, add = FALSE, x.ret = FALSE)$eig

# Perform symmetric multidimensional scaling (SMACOF)
resm_eurociti <- smacofSym(eurociti, 2, )

# Print the SMACOF result
resm_eurociti

# Display a summary of the SMACOF result
summary(resm_eurociti)

# Plot the 2D representation of the data
plot(resm_eurociti, main = "smacofSym(eurociti, 2)")
