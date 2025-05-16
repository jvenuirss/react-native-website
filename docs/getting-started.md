import React, { useState } from 'react';
import { SafeAreaView, Text, TouchableOpacity, StyleSheet } from 'react-native';

const frases = [
  "Com você, as coisas parecem fazer mais sentido, Eli.",
  "Eu te amo, nunca se esqueça disso.",
  "Mesmo que as coisas estejam meio embaralhadas, igual esse código de iniciante,",
  "eu me comprometo a melhorar — por nós."
];

export default function App() {
  const [index, setIndex] = useState(0);

  const nextFrase = () => {
    setIndex((prev) => (prev + 1) % frases.length);
  };

  return (
    <SafeAreaView style={styles.container}>
      <Text style={styles.frase}>{frases[index]}</Text>
      <TouchableOpacity style={styles.button} onPress={nextFrase}>
        <Text style={styles.buttonText}>Próxima frase</Text>
      </TouchableOpacity>
    </SafeAreaView>
  );
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    backgroundColor: '#ffe4e6', // rosa claro
    justifyContent: 'center',
    alignItems: 'center',
    padding: 20,
  },
  frase: {
    fontSize: 20,
    color: '#d6336c', // rosa escuro
    textAlign: 'center',
    marginBottom: 40,
    fontWeight: '600',
  },
  button: {
    backgroundColor: '#d6336c',
    paddingVertical: 12,
    paddingHorizontal: 30,
    borderRadius: 25,
  },
  buttonText: {
    color: '#fff',
    fontWeight: '700',
    fontSize: 16,
  },
});
