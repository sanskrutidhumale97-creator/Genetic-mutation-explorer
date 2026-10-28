# Genetic Mutation Explorer 🧬

A beginner-friendly Python project to detect differences between DNA sequences.

## Features
- Compare DNA sequences
- Identify mutations
- Learn genetics with coding

## Language
Python
# Genetic Mutation Explorer 🧬
# DNA Mutation Detection using Python

def compare_dna(dna1, dna2):
    dna1 = dna1.upper().strip()
    dna2 = dna2.upper().strip()

    valid_bases = set("ATGC")

    if not dna1 or not dna2:
        print("Error: DNA sequences cannot be empty.")
        return

    if not set(dna1).issubset(valid_bases):
        print("Error: First sequence has invalid DNA bases.")
        return

    if not set(dna2).issubset(valid_bases):
        print("Error: Second sequence has invalid DNA bases.")
        return

    print("\n🧬 DNA MUTATION REPORT")
    print("-" * 35)
    print("Original DNA :", dna1)
    print("Mutated DNA  :", dna2)

    if len(dna1) != len(dna2):
        print("Sequence lengths are different.")
        print("Possible insertion or deletion detected.")

    common_length = min(len(dna1), len(dna2))
    mutations = 0

    for i in range(common_length):
        if dna1[i] != dna2[i]:
            mutations += 1
            print(
                f"Position {i + 1}: "
                f"{dna1[i]} -> {dna2[i]}"
            )

    print("-" * 35)
    print("Total differences:", mutations)
    print("Length difference:", abs(len(dna1) - len(dna2)))

    if mutations == 0 and len(dna1) == len(dna2):
        print("No differences found!")
    else:
        print("DNA sequence differences detected.")

    print("Note: This is an educational tool,")
    print("not a clinical genetic diagnosis.")


def main():
    print("GENETIC MUTATION EXPLORER")
    print("=" * 35)

    original = input("Enter original DNA sequence: ")
    mutated = input("Enter mutated DNA sequence: ")

    compare_dna(original, mutated)


if __name__ == "__main__":
    main()
