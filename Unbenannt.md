x = np.arange(0, 1.1, 0.1)

a = np.ones(len(x)-1, dtype=float)

a[-1:] = 0.1

a[0:] = 0.1

A = np.zeros([len(x), len(x)])

  

for i in range(1, len(x)-1):

    A[i, i-1] = a[i-1] / (x[i]- x[i-1]) / (x[i+1]- x[i-1]) / 2

    A[i, i+1] = a[i] / (x[i+1]- x[i]) / (x[i+1]- x[i-1]) / 2

    A [i,i] = -(A[i,i-1]+A[i,i+1])


# Festlegen von Neumann und Dirichlet-Randbedingungen

A[0,0]=1

A[0,1] = 0

A[-1,-1] = 1

A[-1,-2] = -1

  

plt.matshow(A)

plt.colorbar()


f = np.ones_like(x)

f[0] = 1

f[-1] = -1

f


u = np.linalg.solve(A, f)

u


plt.plot(x, u, label = "A")

plt.legend(loc = 'best')

plt.show()


xAna = np.linspace(x[0], x[-1], 10)

  

#Randbedingungen festlegen

uL = 1

gR = -1

  

#analytische Lösung berechnen

uAna = uL + (gR+x[-1]-x[0])*xAna - xAna**2/2

  
  

plt.plot(xAna, uAna, "-", label = "anlytic")

plt.plot(x, u, 'r.', label = "numeric")

plt.legend()

plt.grid()