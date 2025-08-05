import React, { createContext, useContext, useState } from 'react';

// Crear el contexto
const ThemeContext = createContext();

// Proveedor del tema
export const ThemeProvider = ({ children }) => {
  // Tema por defecto (Interbank)
  const [theme, setTheme] = useState({
    primary: '#007A3D',        // Verde institucional
    secondary: '#FED100',      // Amarillo brillante
    logo: 'https://via.placeholder.com/120x40?text=LOGO',
    name: 'Banca Escolar'
  });

  // Función para actualizar el tema
  const updateTheme = (newTheme) => {
    setTheme(prev => ({
      ...prev,
      ...newTheme
    }));

    // Aplicar colores a variables CSS
    document.documentElement.style.setProperty('--primary', newTheme.primary || prev.primary);
    document.documentElement.style.setProperty('--secondary', newTheme.secondary || prev.secondary);
  };

  return (
    <ThemeContext.Provider value={{ theme, updateTheme }}>
      {children}
    </ThemeContext.Provider>
  );
};

// Hook personalizado para usar el tema
export const useTheme = () => useContext(ThemeContext);
